# Intro To Linux 10/15

In this document, we will run through some basic bash commands.

## pwd
_print working directory_

```
$ pwd
/home/lastname
```

Prints the full pathname of the current working directory

## ls
_list_

```
$ ls
bin
classes
sample.txt
```

List all directories and files in the current working directory

## mkdir
_make directory_

```
$ mkdir CoSMOWorkshop
$ ls
CoSMOWorkshop
```

Create a new empty directory

## cd
_change directory_

```
$ cd CoSMOWorkshop/
$ pwd
/home/lastname/CoSMOWorkshop/
```

Move into the specified directory. *Hint:* use `cd ..` to move up to the parent directory

## touch

```
$ touch sample.txt
$ ls
sample.txt
```

Updates the timestampe of a file (??), can be used to create a new, empty file

## cp
_copy_
```
$ cp sample.txt copied.txt
$ ls
copied.txt sample.txt
```

Used to make a copy of a file, with a new name.

## mv
_move_
```
$ mkdir cloned
$ mv copied.txt cloned/
$ ls cloned/
copied.txt
```

Used to move a file to a new location. *Hint:* can also be used to rename a file `mv file.txt new_name.txt`

## rm
_remove_
```
$ rm copied.txt
$ ls
$
```
Used to remove a specified file. *Hint:* can be used to remove a directory by specifying `rm directory --recursive`

## nano

```
$ nano sample.txt
```
Used to edit files. Add changes, `Ctrl+O` to write those changes, `Ctrl+X` to exit.

## vim

```
$ vim sample.txt
```
Another option for a text editor. Press `i` to insert. When finished, `ESC` and `:wq` to write and quit.

## cat
_concatenate_
```
$ cat sample.txt [addtl files]
```

Concatenates multiple files and prints to standard output. *Hint:* cat is also used to print the output of a single file.

## --help
Add this argument after any bash command to get helpful information about that command.

```
$ ls --help
Usage: ls [OPTION]... [FILE]...
.......
```

