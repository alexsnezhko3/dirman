# DirMan

DirMan is a terminal-based file management system for Windows. Its interface mimics that of GUI file management systems such as
Windows File Explorer. Such an interface makes it much simpler to visualize and manipulate directory structures directly from the
terminal. Viewing and manipulating directory structures from a command-line environment can be a tedious task, and this tool aims
to simplify this process.

Here is an example of DirMan running on this project's directory tree from Command Prompt:
![](https://github.com/alexsnezhko3/dirman/blob/master/dirman.png)

The directory tree is pictured on the left half of the interface and the files in the currently selected directory on the right half.
As pictured here, there are also arrows that appear on the edges of each panel of the view, indicating that there is more content in
this panel that can be "scrolled" to in order to see.
The area to enter commands to DirMan is on the bottom line of the interface.

## Commands

### Enter Directory
`enter <directory>`: this command is used to change the currently selected directory.

### Close Directory
`close <directory>`: this command is used to 'close' a directory in the tree. Closed directories do not have their child directories
displayed in the directory tree panel.

### Open Directory
`open <directory>`: this command is used to re-open a previously closed directory, so its child directories are once again shown.

### Move File
`move <file> <new_directory>`: this command is used to move a file from the currently selected directory into a new directory.

### Copy File
`copy <file> <new_directory>`: this command is used to copy a file from the currently selected directory into a new directory.

### Rename File/Directory
`rename <file|directory> <new_name>`: this command is used to rename a file or directory.

### Create File/Directory
`new [file|directory] <name>`: this command is used to create a new file or a new directory and place it into the selected directory.

### Remove File/Directory
`remove <file|directory>`: this command is used to remove a file from the selected directory or directory in the tree.

### Quit
`q`: this command is used to exit the program.

## Working with directories

DirMan makes working with directories very simple. Instead of needing to specify the entire absolute/relative path of a directory
to work with it, one can simply type the name of the directory when attempting to access it.
For example, let's say our directory tree looks like this:
```
root
├─ dir1
│  └─ dir2
└─ dir2
```

If we wanted to enter `root/dir1/dir2`, we could simply input `enter dir2`. This will then prompt us to disambiguate which directory we are
referring to. The disambiguation process begins by DirMan printing the different possible directories that could satisfy this query,
and the user will be asked to input the number associated with the directory they were intending to reference:
```
root
├─ dir1
│  └─ dir2: 0
└─ dir2: 1
```
Inputting `0` now will result in `root/dir1/dir2` being selected

DirMan is written in Rust. As of now, DirMan can be only be built and run with the Rust `cargo` utility.
