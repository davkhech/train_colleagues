## Shell
A shell is a special-purpose program designed to read commands typed by a user and execute appropriate programs in response to those commands. Such a program is sometimes known as a command interpreter.
On UNIX systems shell is a process and different users can run different shells simultaneously.

There are different shells
1. Bourne shell - sh
2. C shell - csh
3. Korn shell - ksh
4. Bourne again shell - bash
5. zsh

There are frameworks to make your shell more effective. They add functionality, helpers, plugins, themes to your environment. The two I know are "Oh my Zsh" and "Oh my Bash".

To run command in shell just type it and then press enter. E.g. `whoami`.

The most helpfull command is `man`. It prints out the manual of the command it follows. For example if you want to see what options are available for `whoami` type `man whoami`.

We can group the commands into "categories"
#### terminal navigation commands
* `pwd`
* `cd`
* `ls`
* `locate`
* `du`
* `df`

#### displaying file contents
* `cat`
* `more`
* `less`
* `head`
* `tail`

#### file and directory manipulation
* `touch`
* `mkdir`
* `cp`
* `mv`
* `rm`

#### extract, sort, filter, modify
* `grep`
* `sort`
* `wc`
* `cut`
* `awk`
* `sed`

#### file permissions commands
* `chown`
* `chgrp`
* `chmod`

### Input/output redirections
You can connect commands together so that output of the first command becomes input of the other command without creating of intermediate file. This can be done using pipe. In unix pipe is denoted by `|`. For example `cat README.md | grep e`.

Output redirection is done with `>`. 
```     ls > files      ```

We can also append to an existing file with `>>`. 
```     echo new line >> files      ```

Input redirection is done with `<`.
```     wc -l < files       ```

Here documents `<<`.

To discard the output of the command redirect it to `/dev/null`.
``` cat files > /dev/null ```

You can also merge input or output streams with `n <& m` or `n >& m`.
Normally the STDIN is 0, STDOUT is 1 and STDERR is 2.

### Configure shell
There are different bash configuration files in linux.
- `/etc/profile` system-wide initialization file executed during login
- `/etc/bash.bashrc` system-wide initialization file executed for each bash shell launched
- if `~/.bash_profile` or `~/.bash_login` file exists it is executed after `/etc/profile` during login, otherwise the `~/.profile` is executed
- `~/.bashrc` this file is executed when interactive shell starts
- `~/.bash_logout` is executed during logout

There are environment variables that can be accessed via your shell or the programs you run through shell. To see all available evironment variables do `env`.
For example if you do `env | grep USER` you'll see your log in user name.
You can print the values of your environment variables as well `echo $USER`

You can add enviornment variables by exporting them `export $MY_VAR=42`.

The variable that shows your user's folder is `HOME` and when you type `cd ~` it looks to `HOME` to know the home folder path.

When you type any program to run from shell it needs a way to find the program. 
All the executable directories are stored in `PATH` variable. To see the content of your path `echo $PATH`.
You can see that it's a string in `path_1:path_2:path_3:...:path_n` format. When you type the executable name (e.g. `ls`) to run it searches in `path_1` directory (e.g. `/bin`). If executable exists it's executed, otherwise the `path_2` (e.g. `/usr/bin`) is searched.

When you install new software and want to run it from shell, you need to add it's binary's directory to `PATH`. `export PATH=$PATH:/path/to/new/binaries`.
For example you installed the miniconda and want to use it's python instead of linux's python you need to prepend the minconda python path to `PATH`.
`export $PATH=$HOME/miniconda3/bin`

When you open new terminal, you'll see that the variables you have set disappeared. To make changes permanent you need to write them in `.bashrc` for example so when new terminal is open all the variables will load again.

You can alias a command with a token. For example if you do `alias l='ls -alh'` and then type `l` in shell the `ls -alh` would be executed.

### Shell scripts
We can write scripts that will be executed by our shell program. The shell scripts start with shebang. For example `#!/bin/sh`.

### Resources
1. https://www.tutorialspoint.com/unix/unix-what-is-shell.htm
2. https://ohmyz.sh/
3. https://ohmybash.nntoan.com/
4. The linux programming interface - Michael Kerrisk
5. https://www.geeksforgeeks.org/basic-shell-commands-in-linux/