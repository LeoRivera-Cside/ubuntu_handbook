# Ubuntu Command Handbook

## Key Considerations
- File and Directory names are case sensitive
- Current directory can be is represented as (.) when selecting a Directory.
- To access a file in another directory you must specify the directory as well. 
- Depending on the command, you may be able to select multiple files by listing them separated by a simple space.

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

## File Editing

Open a file using Nano, a straightforward text editor:
> nano <file_name>

Open a file using Vim, a powerful text editor:
> vim <file_name>