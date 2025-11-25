# Ubuntu Directory Hierarchy
As specified by the Linux Filesystem Hierarchy Standard. Treat this doc as personal notes and less as authoritative. Although I am trying to creating a reliable source of information, I would recommend you perform your own research --"Trust, but verify".

### `/` - The root directory

It is: 
- Everything on your system.
- Every other file and directory is found within this one.
It is not:
- Unimportant.

### `/home` - User's home directory

It is: 
- Personal user's directories and files. 
- Includes user-specific data and config.

### `/bin` - Essential binary executables

It is: 
- Executable files belonging to basic shell commands. 
- Accesible by all users in the system.


### `/sbin` - System administration binaries

It is: 
-  where binaries that can only be run by root or sudo user.

It is not:
-

### `/etc` - Configuration files

It is: 
- The system's configuration files. 
- Used primarily by the administrator and services

### `/var` - Variable data logs

It is: 
- where programs store runtime information like logs, user tracking, caches, and other files that system programs create and manage.
It is not:
- cleaned automatically. 

### `/usr` - User programs and data

It is: 
- Executable files, libraries, source of most system programs. 
- Often read only.

### `/lib` - Shared libraries

It is: 
- Code that can be used by executable binaries. 
- Holds libraries used by /bin & /sbin directories.

### `/tmp` - Temporary files

It is: 
- Contains temperary files; those that are deleted when your system restarts. 
It is not:
- a directory you want to store anything important. 

### `/opt` - Third-party applications

It is: 
- used for installing/storing files used by third-party applicaitons that are not available from distribution's repo.

### `/dev` - Device files

It is: 
- Special files related to devices. 
- Something about virtual files?

### `/root` - Home of the root

It is:
- used as the home directory of the root user.
It is not:
- to be confused with the root directory (/).

### `/media` - Mount point for removable media

It is:
- created to access the contents of automatically mounted removable media device.

### `/mnt` - Mount directory

It is:
- created to access manually mounted filesystems.

### `/srv` - Service data

It is:
- where you can find data for service provided by the system.

### Sources
- https://linuxhandbook.com/linux-directory-structure/