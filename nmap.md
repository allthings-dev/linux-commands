# nmap

## Overview
* Nmap is short for Network Mapper. 
* It is an open-source Linux command-line tool that is used to scan IP addresses and ports in a network and to detect installed applications and operating systems.

## Basic Scans
* Ping scan to scan all devies on a subnet
```
nmap -sp 192.168.1.1/24
```

* Scan a single host: Scans a single host for 1000 well-known ports. These ports are the ones used by popular services like SQL, SNTP, apache, and others
```
nmap scanme.nmap.org
```

## Staelth Scan
* Stealth scanning is performed by sending an SYN packet and analyzing the response. 
* If SYN/ACK is received, it means the port is open, and you can open a TCP connection.
* However, a stealth scan never completes the 3-way handshake, which makes it hard for the target to determine the scanning system.
* It is slower
```
nmap -sS scanme.nmap.org
```

## version scan and os scan
* Finding application versions is a crucial part in penetration testing.
* Find an existing vulnerability from the Common Vulnerabilities and Exploits (CVE) database for a particular version of the service. 
* You can then use it to attack a machine using an exploitation tool like Metasploit.
* It is not 100% accurate
```
nmap -sV scanme.nmap.org
```

## Aggressive scan
* It enables OS detection, version detection, script scanning, and traceroute. You can use the -A argument to perform an aggressive scan
* provide far better information than regular scans. 
* Sends out more probes, and it is more likely to be detected during security audits.


## Scan multiple hosts
```
nmap 192.164.1.1 192.164.0.2 192.164.0.2
nmap 192.164.1.*
nmap 192.164.0.1,2,3,4
nmap 192.164.0.0–255

```

## Port scanning

* Basic
```
nmap -p 973 192.164.0.1
nmap -p 76–973 192.164.0.1
nmap --top-ports 10 scanme.nmap.org
```

* Connection Type like TCP, UDP. Here T stands for TCP connection

```
nmap -p T:7777, 973 192.164.0.1
```

### Verbose output
```
nmap -v scanme.nmap.org
```









