#### Session Video
    https://s3.amazonaws.com/kesavkummari.aws/8am_AWSDevOps20230207/20230307_OSBasics_PackageMgmt_BootProcess_Runlevels_FileSystem/video1900079835.mp4
# OS Concepts

- Unix & Linux History & Distributions
- Basic Commands
- Package Management
- File System

# Unix & Linux History & Distributions

#### Unix :
    - Unix is a family of multitasking, multiuser operating systems that originated in the 1960s at Bell Labs.

    - Unix was written in the C programming language and was designed to be portable across different computer hardware architectures.

    - Unix became very popular in the 1970s and 1980s, especially among universities and research institutions.

    - In the 1980s, Unix was commercialized by companies such as Sun Microsystems, HP, and IBM.

#### Linux :
    - Linux, on the other hand, is a Unix-like operating system that was first released in 1991 by Linus Torvalds, a Finnish student.

    - Linux was developed as an open-source operating system, meaning that its source code is available to anyone who wants to modify it. 
    
    - Linux quickly became popular in the 1990s and 2000s, especially among server administrators.

#### There are many different distributions (distros) of Linux, each with its own unique characteristics and features. Some of the most popular Linux distributions include:

    - Debian: A community-driven distribution that is known for its stability and reliability.

    - Ubuntu: Based on Debian, Ubuntu is one of the most popular Linux distros for desktop users.

    - Red Hat Enterprise Linux (RHEL): A commercial distribution that is widely used in enterprise environments.

    - CentOS: A community-driven distribution that is based on RHEL but is free and open-source.

    - Fedora: A community-driven distribution that is sponsored by Red Hat.

    - Arch Linux: A lightweight and flexible distribution that is designed for advanced users.

    - SUSE Linux Enterprise Server (SLES): A commercial distribution that is widely used in enterprise environments.

    - Linux Mint: A user-friendly distribution that is based on Ubuntu.

    - Gentoo: A distribution that is designed for performance and customization.

    - Manjaro: A user-friendly distribution that is based on Arch Linux.

    - Amazon Linux:

    - Oracle Linux:



# Boot Process & Run levels

#### Here's a table comparing the boot process of Windows, Linux, and Unix:

|Process Step | Windows	| Linux	| Unix |
|-------------|---------|-------|-----|
| 1. BIOS/UEFI Firmware	| The BIOS/UEFI firmware initializes hardware devices and checks for system integrity. | The BIOS/UEFI firmware initializes hardware devices and checks for system integrity. | The BIOS initializes hardware devices and checks for system integrity. |
| 2. Bootloader	| The bootloader is responsible for loading the Windows kernel and other system files.	| The bootloader (GRUB, LILO, etc.) loads the Linux kernel and initial RAM disk (initrd). | The bootloader (GRUB, LILO, etc.) loads the Unix kernel and initial RAM disk (initrd). |
| 3. Kernel	| The Windows kernel is loaded and initializes device drivers and system services.	| The Linux kernel is loaded and initializes device drivers and system services. | The Unix kernel is loaded and initializes device drivers and system services. |
| 4. Init System | Windows does not have a separate init system. | Linux uses a system called init or systemd to start system services and daemons.	| Unix uses a system called init or systemd to start system services and daemons. |
| 5. Runlevel/Target | Windows does not use runlevels or targets. | Linux uses runlevels (0-6) or systemd targets to define system states and specify which services to start or stop.|Unix uses runlevels (0-6) or systemd targets to define system states and specify which services to start or stop. |
| 6. Services | Windows services are started by the Service Control Manager (SCM) and can be configured to start automatically or manually. | Linux services are started by the init system or systemd and can be configured to start automatically or manually. | Unix services are started by the init system or systemd and can be configured to start automatically or manually. |
| 7. Graphical User Interface (GUI)	| The Windows GUI is started by the Windows Explorer shell, which is loaded as a user-level process. | The Linux GUI (X Window System) is started as a user-level process and can be customized with different desktop environments (GNOME, KDE, etc.).	| The Unix GUI (X Window System) is started as a user-level process and can be customized with different desktop environments (GNOME, KDE, etc.). |

#### Note: 
    - This table provides a general overview of the boot process for Windows, Linux, and Unix. 
    - The exact details and steps may vary depending on the specific operating system and configuration.

# Windows Linux and Unix Run Levels table

|Run Level | Windows	| Linux | Unix |
|-------------|---------|-------|-----|
| 0 |	System halt/shutdown | System halt/shutdown | System halt/shutdown |
| 1 |	Single-user mode | Single-user mode | Single-user mode |
| 2 |	Not used | User-defined | User-defined |
| 3 |	Multi-user mode with networking	 | Multi-user mode with networking | Multi-user mode with networking |
| 4 |	Not used  |User-defined  | User-defined |
| 5 |	Multi-user mode with networking and GUI | Multi-user mode with networking and GUI	| Multi-user mode with networking and GUI |
| 6 |	System reboot | System reboot | System reboot |


#### Note: 
    
    - Windows does not have traditional runlevels like Linux and Unix. 
    
    - Instead, it has different system states, such as Safe Mode and Normal Mode, which are activated during the boot process. 
    
    - Linux and Unix runlevels can vary depending on the distribution and configuration. 
    
    - Some Linux distributions use systemd targets instead of runlevels. 
    
    - The exact functionality of each runlevel can also vary depending on the specific operating system and configuration.



#### Unix / Linux File System

Unix and Linux file systems are hierarchical in nature and follow a tree-like structure. The root directory is the top-level directory, denoted by a forward slash /. All other directories and files are organized under this directory.

Here's an overview of some of the most commonly used directories in the Unix/Linux file system:

    /bin: Contains essential command-line utilities and programs needed for system boot and recovery.

    /boot: Contains boot loader files, kernel images, and other files needed for system boot.

    /dev: Contains device files, which represent hardware devices on the system.

    /etc: Contains system configuration files and scripts.

    /home: Contains user home directories.

    /lib: Contains shared libraries used by programs in the /bin and /sbin directories.

    /mnt: Contains mount points for file systems that are temporarily mounted.

    /opt: Contains optional software packages installed on the system.

    /proc: Contains a virtual file system that provides information about running processes and system resources.

    /root: The home directory for the root user.

    /sbin: Contains system administration programs and utilities.

    /tmp: Contains temporary files created by system and user processes.

    /usr: Contains user utilities and applications.

    /var: Contains variable data files, such as log files and print spools.

In addition to the directories listed above, there are also several special directories that are denoted by a single dot . or two dots ... The single dot . represents the current directory, while two dots .. represent the parent directory.

Overall, the Unix and Linux file system is designed to be flexible and modular, allowing users and system administrators to easily organize and manage files and directories.


#### Windows File System

The Windows file system is hierarchical in nature and follows a tree-like structure similar to Unix and Linux file systems. However, there are some key differences in the organization and structure of the file system.

Here's an overview of some of the most commonly used directories in the Windows file system:

    C:\: Contains the core operating system files, including system files and directories, the Windows registry, and user profiles.

    C:\Program Files: Contains installed programs and applications.

    C:\Program Files (x86): Contains 32-bit applications installed on a 64-bit version of Windows.

    C:\Windows: Contains Windows system files, drivers, and system-specific applications.

    C:\Users: Contains user profile directories, including documents, downloads, pictures, and music.

    C:\Temp: Contains temporary files created by the system or users.

    C:\System Volume Information: Contains system restore points and related files.

In addition to the directories listed above, there are also several special directories denoted by a single dot . or two dots ... The single dot . represents the current directory, while two dots .. represent the parent directory.

Overall, the Windows file system is designed to be user-friendly and easy to navigate. While there are some differences in the organization and structure of the file system compared to Unix and Linux, the principles of hierarchical organization and a tree-like structure are still present.
