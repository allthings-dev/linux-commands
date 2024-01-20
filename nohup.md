# Nohup

## Overview
* Nohup, short for no hang up is a command in Linux systems that keep processes running even after exiting the shell or terminal.
* Nohup prevents the processes or jobs from receiving the SIGHUP (Signal Hang UP) signal. This is a signal that is sent to a process upon closing or exiting the terminal.

## Comamnd syntax
* Nohup command syntax is as follows:
```
nohup command arguments
```
* Starting a process using nohup. The output of the command has been saved to nohup.out t
```
nohup ./hello.sh

cat nohup.out
```
* Additionally, you can opt to redirect the output to a different file as shown
```
nohup ./hello.sh > output.txt
```
* To redirect to a file and to standard error and output use the > filename 2>&1 attribute as shown
```
nohup ./hello.sh > myoutput.txt >2&1 
```
* Starting a process in the background using Nohup
```
nohup ping google.com &
```
