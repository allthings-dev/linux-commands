# systemctl and systemd

#### The most important and modern distributions have migrated to systemd to manage system services. systemd has a command called systemctl with which you can perform basic tasks.

#### systemctl has to run with root or with sudo privilege

#### References:
* https://documentation.suse.com/smart/systems-management/html/systemd-basics/index.html
* https://www.digitalocean.com/community/tutorials/understanding-systemd-units-and-unit-files

## Commands

#### List services
* sudo systemctl list-units --type service // lists only active servcies
* sudo systemctl list-units --type service -all // lists all services
* sudo systemctl list-units --type=service --state=running // lists all runnign services

#### Start a service
* sudo systemctl start apache2
* sudo systemctl start apache2.service // the .servcie part is optional

#### Stop a service
* sudo systemctl stop apache2

#### Restart a service
* sudo systemctl restart apache2

#### Reload a service's configuration
* sudo systemctl reload apache2

#### Set a service to start with system boot
* sudo systemctl enable apache2

#### Set a service to not start with system boot
* sudo systemctl disable apache2

#### Get status of a service
* sudo systemctl status apache2

#### Check if service is actibe
* sudo systemctl is-active apache2 // return exit status 0 if true

#### Check if service is enabled
* sudo systemctl is-enabled apache2 // return exit status 0 if true



## Files and folders

#### Earlier linux a /etc/rc.d/init.d fodlers to keep scripts that managed a service. That system was called Upstart

#### In systemd, these files are called servcie units and end in .servcie extension. 

#### The servcie unit files are in /etc/systemd/system/ folder

#### Sample service
```
[Unit]
Description=Postfix Mail Transport Agent
After=syslog.target network.target
Conflicts=sendmail.service exim.service

[Service]
Type=forking
PIDFile=/var/spool/postfix/pid/master.pid
EnvironmentFile=-/etc/sysconfig/network
ExecStartPre=-/usr/libexec/postfix/aliasesdb
ExecStartPre=-/usr/libexec/postfix/chroot-update
ExecStart=/usr/sbin/postfix start
ExecReload=/usr/sbin/postfix reload
ExecStop=/usr/sbin/postfix stop

[Install]
WantedBy=multi-user.target
```

## Targets

#### Runlevels are replaced by targets and these group a set of services that run in a target

#### List targets
* systemctl list-units --type target
* systemctl list-units --type target --all

#### Display default target unit. 
* sudo systemctl get-default
* This is at /etc/systemd/system/default.target

#### Sets default target unit
* sudo systemctl set-default name.target




## System management commands

#### Shutdown
* sudo systemctl poweroff

#### Halt
* sudo systemctl halt

#### Reboot
* sudo systemctl reboot

#### Suspend
* sudo systemctl suspend

#### Hibernate
* sudo systemctl hibernate


