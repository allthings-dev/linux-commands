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

