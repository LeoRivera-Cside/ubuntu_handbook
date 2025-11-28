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

## Sources

https://linuxhandbook.com/redirection-linux/
https://linuxhandbook.com/linux-file-permissions/