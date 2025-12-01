# Ubuntu Command Handbook

## Definitions
 - User, when relating to linux file permissions, is the owner of the file. Usually the creator of said file, but ownership can change. 
 - Groups, when relating to lnux file permissions, consists of several users in a system. Several groups can be created and their users managed. 
 - Other, when relating to linux file permissions, can be considered as another group for anyone with access to the system.
 - Read, when relating to linux file permissions, means a user view or copy file or directory contents. 
 - Write, when relating to linux file permissions, means a user can modify files or add/delete files into a directory (this needs execute permission as well).
 -Execute, when relating to linux file permissions, means a user can run a file or enter a directory.

## Key Considerations
- File and Directory names are case sensitive
- Current directory can be is represented as (.) when selecting a Directory.
- To access a file in another directory you must specify the directory as well. 
- Depending on the command, you may be able to select multiple files by listing them separated by a simple space.
- Path environment variable is an alternatuve to having to type full directory paths for executing a program/script. 
-

## Navigation
Print the working directory:
>pwd

List current subdirectories:
>ls

Change current directory:
>cd <subdirectory_name> 

Change directory to current containing directory:
>cd ..

Use the less application to scroll through pages of a file:
>less <file_name>

## Text Processing

Cut out sections of each line from a file or output and display it on stdout. 
> cut <file_name> [option] [specifics]


## File Management

Create a new empty file
>touch <new_file_name>

Remove a file:
>rm <file_name>

Create a new directory:
>mkdir <directory_name>

sRemove a directory:
>rmdir <directory_name>

Move or rename a file or directory:
> mv <old_source_name> <new_destination_name>

Copy a file or directory:
> cp <source_name> <destination_name>

Display text or strings in the terminal:
> echo <variable>

## Working with files

Open a file using Nano, a straightforward text editor:
> nano <file_name>

Open a file using Vim, a powerful text editor:
> vim <file_name>

Join several input files by sending their content on standard output:
> cat <file_name> ...

## Path Directory

Print your current path:
> echo "$PATH"

Getting a path of a linux command:
> whereis <command>

Display help about commands:
> whatis <command>
    or
> man <command>
    or
> help <command>

Temporarily add a directory to a Path variable:
> $ export PATH="/bin/myscripts:$PATH"

Permanently add a directory to $PATH:
    Open the text editor to edit .bashrc:
> $ nano ~/.bashrc
    then add to the end of the file:
> export PATH="/bin/myscripts:$PATH"
    lastly, save changes, exit, and execute the following:
> $ source ~/.bashrc

## Standard I/O & Redirection

Redirect the output of a command to a file. If the file does not exists, the shell will create it. 
> <command> > <file-name>

To append a redirect to a file, instead of overwriting it:
> <command> >> <file_name>

Pipe redirection: send the stdout of a command into the stdin of another command. Can be chained into multiple commands.
> <command_a> | <command_b> 

Redirect the content of the file to stdin of theh command
> <command> < <file_name>

Redirect error output to a file:
> <command> 2> <file_name>

## Linux File Permissions

Check file permissions. You will see a 9 character pattern. First three relate to the user owner, the following three to the group owner, and the last three for the other group (R = read, W = write, X = exeecute, - = no permissions)
> stat [option] <files>

Change file permissions
> chmod [abolute mode permissions] <file_name>
> chmod [symbolic mode permissions] <file_name>

Change a file's user-owner in Linux: 
> chown <new_user_name> <file_name>

Change file user-group in linux:
> chown :<new_user_group> <file_name>
> chgrp <new_user_group> <file_name>


## Compression

create a tar archive; a format used to organize and manage multiple files into a single archive:
> tar cvf <archive_name.tar> <directory_to_archive/>

to extract a tar archive:
> tar xvf <archive_name.tar>

To create a gzip comptressed tar file; a size reduction format optimized for speed:
> tar cvzf <archive_name.tar.gz> <directory_to_archive/>

To create a bzip2 compressed tar achive, a size reduction format optimized for size:
> tar cvjf <archive_name.tar.bz2> <directory_to_archive/>

## File links

Create a hard link (a mirror copy of a file in a Linux/Unix system, essentially an additional name for the same file data):
> ln <source_name> <link_name>

Create a soft link (a shortcut pointing to a file in a Linux/Unix system):
> ln -s <source_name> <link_name>


#Processes

Find the ID of a running process (aka PID):
> pidof <process_name>

Resumes stopped job keeping it in the foreground
> fg <%process_ID>

Resume stopped job while keeping it in the background. 
> bg <%process_ID>

To close the terminal without stopping commands:
> disown <%process_ID>

stop command from running:
> kill <%process_ID>

Show all ongoing processes:
> top

Show information about currently running processes:
> ps <process_name>
> ps <process_ID>

Show information about currently running processes with Priority (PR) & Nice (NI) values:
> ps -elf

Start a new process while specifying a priority. -20 (highest) to 19 (lowest).
> nice -n [nice_value] <PID>

Modify the nice value without restarting a process. -20 (highest) to 19 (lowest).
> renice -n [nice_value] <PID>

Display free disk space across all file systems: 
> df

Display free and used memory on the system:
> free

Terminate a process gracefully: 
> kill -15 <process_ID>

Kill a process forcefully:
> kill -9 <process_ID>

Fork a process to create an independent copy of another process (along w/ memory & resources) using a different PID and isolated from the original. 
> '#include <unistd.h>
pid_t fork(void)'

## User Management

Create a new user:
> sudo useradd <user_name>

Create a new user with a home directory:
> sudo useradd -m <user_name>

Set a user's password:
>sudo passwd <user_name>

Modify a user's properties:
> sudo usermod [options] <user_name>

Add a user to a group:
> sudo usermod -aG <group> <user>

Remove a user from a group:
> sudo gpasswd --delete <user> <group>

Lock a user's account:
> sudo passwd -1 <user>

Unlock a user's account:
> sudo passwd -u <user>

Switch to another user's account (you'll be prompted for a password if one exists): 
> su - <user>

Delete a user: 
> sudo userdel -r <user>

## Group management
 
Create a group:
> sudo groupadd [options] <group> 

Change group ID:
> sudo groupmod -g <group_ID> <group>

Change a group's name: 
> sudo groupmod -n <new_name> <old_name>

Delete a group:
> sudo groupdel <group>

## Service Management

start a service:
> sudo systemctl start <service_name>

stop a service
> sudo systemctl stop <service_name>

restart a service:
> sudo systemctl restart <service_name>

check a service's status:
> systemctl status <service_name>

## Package Management

Upgrade a system:
> apt-get update

Refresh available package versions:
> sudo apt update

Search for a package to install:
> apt search <package_name>

Install a package
> sudo apt install <package_name>

List installed packages:
> sudo apt list --installed

Uninstall a package:
> sudo apt purge <package_name>

Remove any unneeded dependencies:
> sudo apt autoremove

list upgradable packages:
> apt list --upgradable

Update all installed packages:
> sudo apt upgrade

Update a specific package:
> sudo apt install --only-upgrade <package_name>

Hold a package from being upgraded:
> sudo apt-mark hold <package_name>

Allow a package to be upgraded again: 
> sudo apt-mark unhold <package_name>

## Networking

List available network interfaces:
> ifconfig

Manage network interfaces, routing, and tunnels
> ip 

Send a series of data packets to a host and await a response. Used to troubleshoot connections:
> ping <host>

List open ports and measure their performance:
> netstat [options]

list open ports:
> ss [options]

Query a DNS server:
> nslookup <host>

Configure firewalls with iptables: (unfinished)
> sudo iptables [options]......

Monitor TCP/IP traffic, capturing and analyzing network traffic to identify networking issues:
> sudo tcpdump [option] <network_interface>

Send a data packet to a destination and list all intermediate routers/hops along the way. 
> traceroute <host>

Map a computer network: 
> nmap [options] <ip_address>

Restart the networking service:
> sudo systemctl restart networking

## Containerization

Limit the resources available to a client-user:
> ulimit [option]

Allocate resources among hierarchically ordered groups of processes:
> cgroup [option]

## Sources

https://linuxhandbook.com/redirection-linux/
https://linuxhandbook.com/linux-file-permissions/
https://centlinux.com/linux-networking/