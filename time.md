# time command

## Overview
* ‘time’ command in Linux is used to execute a command and prints a summary of real-time, user CPU time and system CPU time spent by executing a command when it terminates.
* ‘real‘ time is the time elapsed wall clock time taken by a command to get executed
* ‘user‘ and ‘sys‘ time are the number of CPU seconds that command uses in user and kernel mode respectively

## Basic example
```
time sleep 3

real    0m3.063s
user    0m0.000s
sys     0m0.000s
```

## Another example
```
time wget http://example.com/file.zip
```

## Send output to a file
```
time -o timing.log ls -l
```

## Help options
```
help time
```
