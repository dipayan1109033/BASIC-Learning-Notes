# Command prompt (cmd) commands <!-- omit from toc -->

**Table of Contents**
- [Basic CMD commands](#basic-cmd-commands)
  - [`help`](#help)
    - [`help [command]`](#help-command)
  - [`cls`](#cls)
  - [`dir`](#dir)
  - [`cd [path]`](#cd-path)
    - [`cd [/d] [drive:][path]`](#cd-d-drivepath)
    - [`cd ..`](#cd-)
    - [`cd\`](#cd)
    - [`[drive]:`](#drive)
  - [`mkdir [drive:]path`](#mkdir-drivepath)
  - [`copy [path\file.ext] [path\newfile.ext]`](#copy-pathfileext-pathnewfileext)
  - [`del`](#del)
  - [`rmdir`](#rmdir)
    - [`rmdir /s`](#rmdir-s)
- [References](#references)


## Basic CMD commands


### `help`
-	Displays a summary of commands
#### `help [command]`
-	Displays help information on that [command].

### `cls`
-	Clear the screen

### `dir`
-	Displays a list of files and subdirectories in a directory.

### `cd [path]`
-	Displays the name of or changes the current directory.
#### `cd [/d] [drive:][path]`
-   Use the `/d` switch to change current drive in addition to changing current directory for a drive.
#### `cd ..` 
-   Change directory to one lever up (one level higher) parent directory 
#### `cd\`
-   Change to root directory of the current drive
#### `[drive]:`
-   Change directory to the drive `[drive]:\`

### `mkdir [drive:]path`
-	Creates a directory.
rename [drive:][path]filename1 filename2.
-	Renames a file or files.

### `copy [path\file.ext] [path\newfile.ext]`
-	Copies one or more files to another location.

### `del` 
-	Deletes one or more files.


### `rmdir`
- Removes (deletes) a directory.

#### `rmdir /s`      
- Removes all directories and files in the specified directory in addition to the directory itself.  Used to remove a directory tree.
  
## References


[20 best Command Prompt (CMD) commands](https://www.digitalcitizen.life/best-cmd-commands/)

[CMD: 11 basic commands](https://www.digitalcitizen.life/command-prompt-how-use-basic-commands/)
