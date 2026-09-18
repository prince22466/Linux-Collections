# Kernel Dev

kernel development happens in the kernel source tree; /proc and /sys are runtime interfaces into the kernel you built.

Kernel source tree(ie, arch/arm64/, drivers/, drivers/gpu/, drivers/media/, drivers/sound/)  
    ↓  
you WRITE kernel code here


/proc  
/sys  
/debugfs  
/tracing  
    ↓  
you OBSERVE or INTERACT with the running kernel here. /proc and /sys are runtime interfaces into the kernel been built.

-----------------------------------------------------------------------------------------------------------------

# Linux File
Linux presents files and mounted filesystems through a single directory hierarchy rooted at /.  
Other filesystems can be mounted at directories within that hierarchy, while devices and kernel interfaces can also be represented through special filesystem objects such as /dev and /proc.

| Directory | Common Usage | Description |
|---|---|---|
| / | Root of the system | The starting point of the entire directory tree containing all other folders. |
| /home | Personal user workspace | Contains personal subfolders for user accounts (e.g., /home/john), including downloads, documents, and individual user data. |
| /root | Administrator workspace | The home directory for the administrator (root user), keeping administrative files separate from the main root (/) directory. |
| /bin | Essential user binaries | Holds basic command-line tool executables like ls, cp, mv, cat, and mkdir required for basic system operations. On systems using a merged /usr, /bin may effectively map to /usr/bin, so don't imply it must contain independent files.|
| /sbin | System binaries | Contains administrative commands (e.g., networking, system recovery, disk management) used primarily by system admins. Modern systems may merge it with /usr/sbin or even treat sbin and bin equivalently. |
| /etc | System settings | Stores configuration files for system settings, applications, network interfaces, and services (e.g., SSH, DNS). |
| /usr | User programs & software | Secondary hierarchy housing user utilities, libraries, and applications installed for overall system operations. |
| /var | Variable/changing data | Stores data that continuously grows and changes, such as system logs (/var/log), database files, mail queues, and cache files. |
| /media | Removable storage | Default location where system-recognized removable media (like USB drives or DVDs) are  mounted. |
| /mnt | Manual storage mounts | Folder used by administrators to manually mount temporary external storage, network shares, or secondary disks. |
| /dev | Device representation | Contains special device files that treat hardware components (like hard drives /dev/sda, mice, or terminals) as files. They are filesystem interfaces/device nodes through which programs interact with devices. |
| /proc | Live process/kernel info |It is a *pseudo-filesystem/interface to kernel* data structures, It exposes process and kernel/system information such as /proc/PID, /proc/cpuinfo, and /proc/meminfo. |
| /boot | Boot sequence files | Contains essential components needed to start up Linux, including the Linux kernel, bootloader, and startup configuration. |
