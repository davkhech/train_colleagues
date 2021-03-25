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

### Shell scripts
We can write scripts that will be executed by our shell program. The shell scripts start with shebang. For example `#!/bin/sh`.

### Resources
1. https://www.tutorialspoint.com/unix/unix-what-is-shell.htm
2. https://ohmyz.sh/
3. https://ohmybash.nntoan.com/
4. The linux programming interface - Michael Kerrisk
5. https://www.geeksforgeeks.org/basic-shell-commands-in-linux/