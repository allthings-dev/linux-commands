# netstat

## Overview
* The netstat command means network statistics, 
* It is used to display very detailed information about how your computer is communicating with other computers or network devices.


## Syntax
```
netstat [-a] [-b] [-e] [-f] [-n] [-o] [-p protocol] [-r] [-s] [-t] [-x] [-y] [time_interval] [/?]
```

### Basic comamnd
* Execute the netstat command alone to show a relatively simple list of all active TCP connections which, 
* For each one, will show the local IP address (your computer), the foreign IP address (the other computer or network device), 
* Along with their respective port numbers, as well as the TCP state.
```
netstat
```

### Show fqdn
```
netstat -f
```

### List all connection types
```
netstat -a
```

### Sho process id as well for each conenction
```
netstat -o
```


### Shwo protocol specific statistics
```
netstat -s -p tcp -f


TCP Statistics for IPv4
 Active Opens = 77
 Passive Opens = 21
 Failed Connection Attempts = 2
 Reset Connections = 25
 Current Connections = 5
 Segments Received = 7313
 Segments Sent = 4824
 Segments Retransmitted = 5
Active Connections
 Proto Local Address Foreign Address State
 TCP 127.0.0.1:2869 VM-Windows-7:49235 TIME_WAIT
 TCP 127.0.0.1:2869 VM-Windows-7:49238 ESTABLISHED
 TCP 127.0.0.1:49238 VM-Windows-7:icslap ESTABLISHED
 TCP 192.168.1.14:49194 75.125.212.75:http CLOSE_WAIT
 TCP 192.168.1.14:49196 a795sm.avast.com:http CLOSE_WAIT
 TCP 192.168.1.14:49197 a795sm.avast.com:http CLOSE_WAIT
```



### Show Updated Network Stats
* In this example, netstat shows some basic network interface statistics [-e] that are continually updated in the command window every five seconds [-t 5].
```
netstat -e -t 5


Interface Statistics
 Received Sent
 Bytes 22132338 1846834
 Unicast packets 19113 9869
 Non-unicast packets 0 0
 Discards 0 0
 Errors 0 0
 Unknown protocols 0
Interface Statistics
 Received Sent
 Bytes 22134630 1846834
 Unicast packets 19128 9869
 Non-unicast packets 0 0
 Discards 0 0
 Errors 0 0
 Unknown protocols 0
```
