#### Session Video:
    https://s3.amazonaws.com/kesavkummari.aws/8am_AWSDevOps20230207/20230308_FS_VI/video1745940216.mp4
    
#### 
    File System

    Text Editors : vi / vim 


# Windows and Linux File System

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


# Text Editors in Linux 

####
    1. Insert Mode: 
        - i = inserts the text at current cursor position
        - I = inserts the text at beginning of line
        - A = Appends the text at end of line
        - o = inserts a line below current cursor position
        - O = inserts a line above current cursor position
        - r = replace a single char at current cursor position

    2. Execute Mode:
        - :q       = quit without saving
        - :!       = forcefully
        - :q!	     = quit forcefully without saving
        - :w       = save
        - :wq      = save & quit
        - :wq!     = save, quit forcefully
        - :se nu   = setting line numbers for reading only 
        - :se nonu = Removing the line numbers
        - :20      = Press enter to go to specific line like 20
        - :6,10 w! <new_file> : We can copy desire lines     [ :12,18 w! >>/root/Desktop/mac.txt ] 
        - :%s/cursor/devops/g : Search and Replace 

    3. Command Mode:
        - dd   = Deletes a line 
        - ndd  = Delete 2 lines  # 2dd 
        - yy   = Copy a line
        - nyy  = copies 3 lines  # 3yy # 100yy
        - p    = put (paste deleted or copied text)
        - u    = undo (can undo 1000 times)
        - ctrl+r = Redo
        - G      = Moves cursor to last line of file
        - /<word to find> = To search for a particular word.

#### Q?
    - 
