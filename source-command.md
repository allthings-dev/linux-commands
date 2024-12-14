# Source Command

## Overview
* Reference: https://superuser.com/questions/176783/what-is-the-difference-between-executing-a-bash-script-vs-sourcing-it
* When you source the script you are typing the commands in your current shell. Any changes to the environment will take effect and stay in your current shell.
```
source some_script
```
* The file "some_script" does not need to be executable. It can be in current directoty or in $PATH
* "source" comamdn is an alias to dot (.)
```
. some_script
```

## Other ways to run scripts and differences in these methods
* Directly execute a script. When you execute the script like below, you are opening a new shell, type the commands in the new shell, copy the output back to your current shell, then close the new shell. Any changes to environment will take effect only in the new shell and will be lost once the shell is closed. This will execute myscript provided that the file is executable and located in the current directory. The leading dot and slash (./) denotes the current directory.
```
./myscript
```
* Using "exec". exec myscript. This will terminate the current shell and then execute myscript in place of the terminated shell. That means when myscript is done there no shell to return to. exec is powerful but rarely needed.
```
exec myscript
```
