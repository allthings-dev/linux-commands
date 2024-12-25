# proxy

## Overview
* Whenever you run a command-line tool that needs to access the internet, it looks for the http_proxy variable

### Basic proxy setting
* Proxies can be set system-wide by settign below env variables
* These variables can be set in bashrc file too
```
$ export http_proxy=http://user:password@proxyserver.com:3128
$ export https_proxy=https://user:password@proxyserver.com:3128
```

### Proxy settign with username/password
```
$ export http_proxy=http://DOMAINUSERNAME:PASSWORD@SERVER:PORT/
```

### no_proxy
* There is no standard that all tools follow. Some tool strip teh leading dot, others don't
```  
export no_proxy="localhost"
export no_proxy="localhost,127.0.0.1,localaddress,.localdomain.com"
export no_proxy='*'
```

### Unset proxy
```
unset http_proxy
unset https_proxy
```
