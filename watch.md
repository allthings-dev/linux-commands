# watch command

## Overview
* The watch command is a built-in Linux utility used for running user-defined commands at regular intervals
* It temporarily clears all the terminal content and displays the output of the attached command, along with the current system date and time.
* By default, the watch command updates the output every two seconds.
* Press Ctrl+C to exit out of the command output. 

## Usage
* Watch output of default, at interval of the default 2 sec
```
$ watch date
```
* Watch at interval of 5 sec
```
$ watch -n 5 date
```
* Highlight differences in output
```
$ watch -d date
```
* Hide the output header which has date, comamnd
```
$ watch -t date 
```
* For comamnds with their own options, quote teh full comamnd
```
$ watch -n 5 'echo "watch command example output"'
```

