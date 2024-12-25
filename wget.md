# wget command

## Overview
* Reference: https://gist.github.com/Dammmien/4af98e05f9c51c2da007cc70d62bf562
* Wget is a command-line utility for downloading files from the web
* With Wget, you can download files using HTTP, HTTPS, and FTP protocols
* wget follows upto 20 redirects by dafault
* Wget provides a number of options allowing you to:
  * download multiple files
  * resume downloads
  * limit the bandwidth
  * recursive downloads
  * download in the background
  * mirror a website
  * and much more

## Usage

### Basic
* Down a file from a url with same name as last part of the url and save it to current folder
* This will save the downloaded file as linux-4.17.2.tar.xz
* If file already exists, wget will save teh file with .N (or 1,2,3 etc) appended to the end
* It will also show verbose output such as dns resolution, progress, time left, fiel size etc
```
$ wget https://cdn.kernel.org/pub/linux/kernel/v4.x/linux-4.17.2.tar.xz
```
### Quiet mode
* To turn off verbose output (progress, dns resolution etc), use option -q
```
$ wget -q https://cdn.kernel.org/pub/linux/kernel/v4.x/linux-4.17.2.tar.xz
```
### Save as adifferent file name
```
wget -O latest-hugo.zip https://github.com/gohugoio/hugo/archive/master.zip
```
### Save in a different folder
```
$ wget -P /mnt/iso http://mirrors.mit.edu/centos/7/isos/x86_64/CentOS-7-x86_64-Minimal-1804.iso
```
### Limit download speed
*  By default, the speed is measured in bytes/second. Append k for kilobytes, m for megabytes, and g for gigabytes.
```
$ wget --limit-rate=1m https://dl.google.com/go/go1.10.3.linux-amd64.tar.gz
```
### Resume download
* This is useful if your connection drops during a download of a large file, and instead of starting the download from scratch, you can continue the previous one
* If the remote server does not support resuming downloads, wget will start the download from the beginning and overwrite the existing file
```
$ wget -c http://releases.ubuntu.com/18.04/ubuntu-18.04-live-server-amd64.iso
```
### Download in background
* To download in the background, use the -b option
* By default, the output is redirected to wget-log file in the current directory. Tail this fiel to see the progress
```
$ wget -b https://download.opensuse.org/tumbleweed/iso/openSUSE-Tumbleweed-DVD-x86_64-Current.iso
```
### Change user-agent
```
$ wget --user-agent="Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0" http://wget-forbidden.com/
```
### Download multiple files
* Each line in the linux-distros.txt should be a url
```
wget -i linux-distros.txt
```
### Download as ftp
```
$ wget --ftp-user=FTP_USERNAME --ftp-password=FTP_PASSWORD ftp://ftp.example.com/filename.tar.gz
```
### Skip ssl certificate check
```
$ wget --no-check-certificate https://domain-with-invalid-ss.com
```
### Sepcify user and password as auth
* The options --user and --password below can be used in case of http as well as ftp (instead of teh more specific --http-user, --ftp-user etc)
* The option --ask-password will prompt for a password
* The username and password can also be specified in bashrc file instead of on command line
```
$ wget --user user --password pass http://example.com/
```
### Use proxy
* The proxy server is set at system level (check teh proxy.md file)
```
wget --proxy-user=USER --proxy-password=PASS https://cdn.kernel.org/pub/linux/kernel/v4.x/linux-4.17.2.tar.xz
```
### To view default http headers
* Use teh option -d
```
$ wget -d http://www.google.com/

GET / HTTP/1.0
User-Agent: Wget/1.12 (linux-gnu)
Accept: */*
Host: www.google.com
Connection: Keep-Alive
```

### Set http headers
```
$ wget -d --header="User-Agent: Mozilla/5.0 (Windows NT 6.0) AppleWebKit/537.11 (KHTML, like Gecko) Chrome/23.0.1271.97 Safari/537.11" --header="Referer: http://xmodulo.com/" --header="Accept-Encoding: compress, gzip" http://www.google.com/
```

### Hit a url with json as input
* When json is provided as a string on command line
* Note that -O is for output and the dash(-) after it means that put output on standard output itself
```
$ wget -O - --post-data='{"some data to post..."}' --header='Content-Type:application/json' 'http://www.example.com:9000/json'
```
* When json is in an input file
```
wget -q -O - --header="Content-Type:application/json" --post-file=foo.json http://127.0.0.1
```

### Verfiy server cert
* FILE iw file with the bundle of CA's.
```
wget --ca-certificate=FILE http://www.google.com/
```

### Provide cleint cert
* FILE is client certificate file
```
wget --certificate=FILE http://www.google.com/  
```



