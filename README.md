# linux-commands
This repository has sample text files for use with linux commands

## Find os name and version
* cat /etc/os-release
```
NAME="Ubuntu"
VERSION="20.04.1 LTS (Focal Fossa)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 20.04.1 LTS"
VERSION_ID="20.04"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=focal
UBUNTU_CODENAME=focal
```
* lsb_release -a # This comamnd may not be available by default on the machine
```
LSB Version:	:core-4.1-amd64:core-4.1-noarch
Distributor ID:	CentOS
Description:	CentOS Linux release 7.4.1708 (Core) 
Release:	7.4.1708
Codename:	Core
```
* hostnamectl
```
Static hostname: nixcraft-www-42
         Icon name: computer-vm
           Chassis: vm
        Machine ID: beb217fbb4324b7d9959f78c279e6599
           Boot ID: 10f00cc5ca614b518a84d1793d0134bc
    Virtualization: qemu
  Operating System: Ubuntu 16.04.3 LTS
            Kernel: Linux 4.10.0-42-generic
      Architecture: x86-64
```
* cat /proc/version
```
Linux version 3.10.0-693.11.6.el7.x86_64 (mockbuild@x86-041.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-16) (GCC) ) #1 SMP Thu Dec 28 14:23:39 EST 2017

```

## Find os kernel version
* uname -r


