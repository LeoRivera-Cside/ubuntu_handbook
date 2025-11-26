# Ubuntu Command Handbook

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
> mv <old_directory_name> <new_directory_name>

Copy a file or directory:
> cp <directory_name>

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

### Standard I/O & Redirection

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

## Sources

https://linuxhandbook.com/redirection-linux/