Linux presents files and mounted filesystems through a single directory hierarchy rooted at /.  
Other filesystems can be mounted at directories within that hierarchy, while devices and kernel interfaces can also be represented through special filesystem objects such as /dev and /proc.

| Directory | Common Usage | Description |
|---|---|---|
| / | Root of the system | The starting point of the entire directory tree containing all other folders. |
| /home | Personal user workspace | Contains personal subfolders for user accounts (e.g., /home/john), including downloads, documents, and individual user data. |
| /root | Administrator workspace | The home directory for the administrator (root user), keeping administrative files separate from the main root (/) directory. |
| /bin | Essential user binaries | Holds basic command-line tool executables like ls, cp, mv, cat, and mkdir required for basic system operations. |
| /sbin | System binaries | Contains administrative commands (e.g., networking, system recovery, disk management) used primarily by system admins. |
| /etc | System settings | Stores configuration files for system settings, applications, network interfaces, and services (e.g., SSH, DNS). |
| /usr | User programs & software | Secondary hierarchy housing user utilities, libraries, and applications installed for overall system operations. |
| /var | Variable/changing data | Stores data that continuously grows and changes, such as system logs (/var/log), database files, mail queues, and cache files. |
| /media | Removable storage | Default location where system-recognized removable media (like USB drives or DVDs) are automatically mounted. |
| /mnt | Manual storage mounts | Folder used by administrators to manually mount temporary external storage, network shares, or secondary disks. |
| /dev | Device representation | Contains special device files that treat hardware components (like hard drives /dev/sda, mice, or terminals) as files. |
| /proc | Live process/kernel info | A virtual file system created in memory by the kernel that provides real-time data on running processes, CPU status, and RAM. |
| /boot | Boot sequence files | Contains essential components needed to start up Linux, including the Linux kernel, bootloader, and startup configuration. |
