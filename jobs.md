# Jobs

## Overview
* A process that connects to the terminal is called a foreground job
* A process that disconnects from the terminal and cannot communicate with the user is called a background job
* The jobs command to list all the jobs that the current shell has invoked
* The shell lists the job ID of each job, along with the status (running, stopped, or otherwise), and the command that started the job.
* The shell considers the most recent job to be the current job, marked with a plus sign.The commands related to job control will apply to the current job.
* All other jobs, marked with a minus sign, are previous jobs.
* Jobs can be referred to by job ID by using the percent sign. Thus, job 1 is referred to as %1, job 2 is %2, and so forth

## Comamnds
* List all running and suspended jobs
```
jobs
```
* To place a job in the background, we can simply add the ampersand character (&) at the end of a shell command.
```
sort < foo > bar &
```
* Suspend a job that is currently connected to the terminal by typing Ctrl-Z
* When a suspended job is stopped, no processing takes place for that job until it gets run, either in the foreground or in the background
* The command bg to place the suspended job in the background. The bg command can accept a job ID as an argument. If no job ID is given, bg assumes we are referring to the current (suspended) job.
```
bg
```
* Reconnect a background job to our terminal with the Linux command fg. If no job ID is given, fg will assume we’re referring to the current (suspended) job.
```
fg
```
* Once we’ve found the job ID of the suspended job with the jobs command, we can then use bg (to run the job in the background) or fg (to run the job in the foreground).
