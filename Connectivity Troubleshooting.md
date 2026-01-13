# Linux Server Connectivity Troubleshooting Guide
_When a remote Linux server is unreachable (not pingable)_

---

_General logical journy of pinging a remote server, some components are integrated in one physical device.

Your App  
  ↓    ↑  
OS Network Stack  
  ↓    ↑  
Local NIC(Local Network Interface Card)  
  ↓    ↑  
Local Gateway  
  ↓    ↑  
ISP(Internet service provider) Edge Router Ingress (Edge Router is boundary router of the current network, Ingress means entry to the ISP network)  
  ↓    ↑  
ISP Core Routers (internal transit inside current ISP network)  
  ↓    ↑  
ISP Edge Routers Exgress (exit the ISP network)  
  ↓    ↑  
Internet Exchange(connections of Edge Routers) / Peering  
  ↓    ↑  
Destination ISP Edge Router (Ingress)  
  ↓    ↑  
Destination Network Core Routers  
  ↓    ↑  
Destination Gateway  
  ↓    ↑  
Remote Server NIC  
  ↓    ↑  
Remote OS Network Stack  
  ↓    ↑  
Remote Kernel (ICMP Reply)  


## 1. Troubleshooting Flowchart

```mermaid
flowchart TD
    A[Start: Server Unreachable] --> B[Ping hostname]
    B -->|Success| Z[Connectivity OK]
    B -->|Name not resolved| C[Check DNS resolution]
    B -->|Timeout| D[Ping IP address]

    C --> E[nslookup / dig]
    E -->|IP resolved| D
    E -->|No IP| F[Check /etc/hosts, resolv.conf, nsswitch.conf]

    D -->|Success| G[DNS issue confirmed]
    D -->|Failure| H[Ping known external host]

    H -->|Success| I[Target server issue]
    H -->|Failure| J[Local machine/network issue]

    J --> K[Check local IP]
    K --> L[Ping gateway]
    L -->|Success| M[Check routing table]
    L -->|Failure| N[Local network / hardware issue]

    M --> O[Check firewall]
    O --> P[Restart network services]
    P --> Q[Escalate to admin / ISP]
