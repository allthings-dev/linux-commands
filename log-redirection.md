# Log Redirection

## Overview
* In Bash and other Linux shells, when a program is executed, it uses three standard I/O streams. Each stream is represented by a numeric file descriptor:
  * 0 - stdin, the standard input stream.
  * 1 - stdout, the standard output stream.
  * 2 - stderr, the standard error stream
* Streams can be redirected using the n> operator, where n is the file descriptor number
* When n is omitted, it defaults to 1, the standard output stream. Below two comamnds are same
```
command > file
command 1> file
```

* 
## Commands
* To redirect stdout of a process to a file in overwrite mode
```
./abc.sh > log/txt
```
* To redirect stdout of a process to a file in append mode
```
./abc.sh >> log/txt
```
* To redirect the standard error (stderr) use the 2> operator
```
command 2> file
```
* Write both stderr and stdout to two separate files:
```
command 2> error.txt 1> output.txt
```
* Redirecting stderr to stdout
```
command > file 2>&1
```
