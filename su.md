# su

## Overview
* su stahnds for substitute user
* It is used to switch to different user account in linux

## "su username" vs "su - username"
* "su username" is used to switch from one user to another user account within the current shell session. When it is used without additional options,
  then it retains the current environment, including the present working directory and user-specific environment variables. It is useful for quick switching between the users without changing the existing environment setup
* "su - username" helps in switching from one user to another user account and starts a new login shell session.
  This command will fully loads the target user’s environment including their login scripts, home directory, and environment variables. It is effective for simulating a full login. It is often used for administrative tasks that requires the target user’s complete environment.
* Below command will login the curernt user as root
```
su - 
```
## Runnign comamnd with "su"
* Below command allows one to execute administrative commands temporarily and then return to regular user permissions.
```
su –c [command] [other_user]
su -c ls user1
```

## su entitlement
* A user can be given "su" privilege by one of 2 methods below

### Method 1
* Run "visudo" as root or as a iser with full sudo privilege. A file opens in text editor whoch has suffiecient comemnts to help edit it and add a user with permission to run all commands or a specific set of commands
* Additionally, add NOPASSWD to the line to all user "su" without needing to type password

### 'Method 2
* Add suer to sudo group using
```
sudo usermod -aG sudo <user>
```

## sudo
* Run just a single command as root or specified sur
```
sudo passwd abc-user

sodo -u user1 ls
```
* su requires password of target user. sudo needs password of current user only.
