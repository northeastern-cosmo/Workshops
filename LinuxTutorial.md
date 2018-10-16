# Intro To Linux 10/15

In this document, we will run through some basic bash commands for file manipulation.

# Prerequisites

For this workshop, we will be connecting to the CCIS machines, so it is necessary that you have your CCIS username and password. 
- Forgot your password? Go [here](https://my.ccs.neu.edu/forgot/password)

### Windows Users:
- Download [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html), an SSH client compatible with Windows
- Open PuTTY > Host Name: "login.ccs.neu.edu" > Open
- Enter your username and password

### Mac/Linux Users:
- In the terminal, `ssh <username>@login.ccs.neu.edu`
- Enter your password



# Terminal Commands

## pwd
_print working directory_

Prints the full pathname of the current working directory
```
$ pwd
/home/lastname
```

## ls
_list_

List all directories and files in the current working directory
```
$ ls
bin
classes
sample.txt
```

## mkdir
_**m**ake **d**irectory_

Create a new empty directory
```
$ mkdir CoSMOWorkshop
$ ls
CoSMOWorkshop
```


## cd
_**c**hange **d**irectory_

Move into the specified directory. *Hint:* use `cd ..` to move up to the parent directory
```
$ cd CoSMOWorkshop/
$ pwd
/home/lastname/CoSMOWorkshop/
```

## echo 
Sends arguments to standard out
```
$ echo "Hello World"
"Hello World"
```
Output from echo can be redirected to a file with `>`, eg: `echo "making a test file" > sample.txt`
Output from echo can also be appended to a file with `>>`, eg: `echo "second line" >> sample.txt`

## touch
Updates the timestamp of a file. Creates new, empty file if none exist
```
$ date -r sample.txt
Mon Oct 15 19:05:33 EDT 2018 
$ touch sample.txt
$ date -r sample.txt
Mon Oct 15 19:07:18 EDT 2018 
```

## cp
_copy_

Used to make a copy of a file, with a new name.
```
$ cp sample.txt copied.txt
$ ls
copied.txt sample.txt
```

## mv
_move_

Used to move a file to a new location. *Hint:* can also be used to rename a file `mv file.txt new_name.txt`
```
$ mkdir cloned
$ mv copied.txt cloned/
$ cd cloned
$ ls
copied.txt
```

## rm
_remove_

Used to remove a specified file. *Hint:* can be used to remove a directory by specifying `rm directory --recursive`
```
$ rm copied.txt
$ ls
$ 
```

## nano
Used to edit files. Add changes, `Ctrl+O` to write those changes, `Ctrl+X` to exit.
```
$ nano sample.txt
```

## vim
Another option for a text editor. Press `i` to insert. When finished, `ESC` and `:wq` to write and quit.
```
$ vim sample.txt
```

## cat
_con**cat**enate_

Concatenates multiple files and prints to standard output. *Hint:* cat is also used to print the output of a single file.
```
$ cat sample.txt
making a test file
second line
```

## man
_**man**ual_

Output the reference manual for a specific function

```
$ man echo
$ man grep > grep.txt
```

## grep
_**g**lobal **r**egular **e**xpression **p**rint_

Search files for lines matching a specified pattern.
```
$ grep "count" grep.txt
    -c, --count
          ......
```
Grep has a ton of optional arguments, read the docs to see what they are!
```
$ grep -c "processor" /proc/cpuinfo
32
```

## sed
_**s**tream **e**ditor_

A powerful tool used to edit input streams, most commonly performing substitutions in text files.

```
$ echo "Linux is cool, I enjoy it." > test.txt
$ sed "s/Linux/CoSMO/" test.txt
CoSMO is cool, I enjoy it.
```
By default, `sed` will only edit the _first_ match on each line, to edit the nth match, do `sed "s/.../.../n"`. To edit ALL matches, `sed "s/.../.../g`

## alias
Lets you assign a shorter name for a complicated (or simple) command

```
$ alias c='clear'
$ alias ..='cd ..'
```

To make these commands permanent, you need to add them to the `~/.bashrc` file, otherwise they will disappear when you start a new session.

## find 
Used to find files/directories with certain characteristics

```
$ find . -name "*.txt
./grep.txt
./sample.txt
$ find . -type 
```

## xargs
_e**x**tended **arg**ument**s**_

Converts standard input into arguments for a command

```
$ ls | xargs cat
```

# Helpful Notations


## --help
Add this argument after a bash command to get helpful information about that command.

```
$ ls --help
Usage: ls [OPTION]... [FILE]...
.......
```

## >
Used to redirect standard output to a new location.

`echo "new text" > new_file.txt`

## >>
Appends standard output to a specified location.

`echo "added text" > existing_file.txt`

## | 
The pipe allows you to pass the output of the command on the left as input to the program on the right. Lets you chain together multiple commands.

`find . -type f | xargs cat`

## $(...)
Allows for command substitution. Whatever is inside of the parentheses is evaluated, before the outer command is run.

`echo "Today is $(date +"%m/%d/%Y")"`
