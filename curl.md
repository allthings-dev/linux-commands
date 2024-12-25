# curl command

## Overview
* curl fetches data from a url
* Supports protocols such as HTTP, HTTPS, FTP, SCP, SFTP, and more
* To get help, use 'curl --help'

## Usage

### Basic usage
* By default, the response gets displays at standard output itself (this is a problem if a file is downloaded using curl, so send output to a file using -o option)
* It shows progress bar, file size by default
```
$ curl https://example.com
$ curl ftp://ftp.example.com/file.zip
```

### Save output to a file
* The option for this is -o (the english small aplhabet) and here teh file name has to be specified
* When using capital alphabet, the file is downloaded with same name as last part of url
```
curl -o linux.tar.gz https://cdn.kernel.org/pub/linux/kernel/v4.x/linux-4.17.2.tar.xz
```

### Extra verbosity
* This will display dns resolution, ssl handshakes, headers, file sizes etc
```
$ curl -v https://jsonplaceholder.typicode.com/todos/1
```
### Silent mode
```
curl -s  -o linux.tar.gz https://cdn.kernel.org/pub/linux/kernel/v4.x/linux-4.17.2.tar.xz
```

### Handling authentication (username and password)
* Curl automatically converts the username:password pair to a base64-encoded string token and adds the Authorization: Basic <base64 token>
```
$ curl -u username:password https://example.com/api
$ curl -u FTP_USERNAME:FTP_PASSWORD ftp://ftp.example.com/
```

### Resume download
* This option -C was not present in gnu bash emulator
```
curl -C - -O ftp://speedtest.tele2.net/1MB.zip
curl -u demo:password -O ftp://test.rebex.net/readme.txt
```

### Limit rate
```
$ curl --limit-rate 1000K -O ftp://speedtest.tele2.net/1MB.zip
$ curl --limit-rate 1m -O https://dl.google.com/go/go1.10.3.linux-amd64.tar.gz
```

### Multiple downloads
* To download multiple files at once, use multiple -O options, followed by the URL to the file you want to download
```
$  curl -O http://mirrors.edge.kernel.org/archlinux/iso/2018.06.01/archlinux-2018.06.01-x86_64.iso  -O https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-9.4.0-amd64-netinst.iso
```

### View default headers and exclude teh body
* The option for this is -I
```
 curl -I https://jsonplaceholder.typicode.com/todos/1
```

### Follow redirects
* Follow redirect till it reaches a final destination
* The option is -L
```
curl http://google.com // this will stop with 301 http code 
curl -L http://google.com // this will follow redirct and get the final page
```

### Change user agent
```
curl -A "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0" https://getfedora.org/
```

### Handling cookies
* By default, when requesting a resource with curl, no cookies are sent or stored.
* To send cookies to the server, use the -b switch followed by a filename containing the cookies or a string
* For example, to download the Oracle Java JDK rpm file jdk-10.0.2_linux-x64_bin.rpm you’ll need to pass a cookie named oraclelicense with value a:
```
$ curl -L -b "oraclelicense=a" -O http://download.oracle.com/otn-pub/java/jdk/10.0.2+13/19aef61b38124481863b1413dce1855f/jdk-10.0.2_linux-x64_bin.rpm
```

### Use specified proxy
* To sue proxy server 192.168.44.1 on port 8888
* If proxy needs username/password, use the capital -U option (note that this is different from teh small -u option which is for the auth of the http server)
```
$ curl -x 192.168.44.1:8888 http://linux.com/
$ curl -U username:password -x 192.168.44.1:8888 http://linux.com/
```

### Change http method
```
$ curl -X PUT www.example.com?id=4
```

### Add http headers
```
$ curl -H "User-Agent: Mozilla/5.0 (Macintosh)" -H "Cache-Control: no-cache"
```

### Post data
```
$ curl -d "option1=value1&option2=value2" -X POST https://www.example.com
```

### Make http hit for json response
```
$ curl -X POST -H "Content-Type: application/json" -d '{"option1":"value1", "option2":"value2"}' https://www.example.com
```










