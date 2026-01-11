# Linux Connectivity Troubleshooting Guide
_When a remote Linux server is unreachable (not pingable)_

---

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
