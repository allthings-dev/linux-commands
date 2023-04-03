# useradd command

#### Reference
* https://linuxize.com/post/how-to-create-users-in-linux-using-the-useradd-command/

#### Only root or users with sudo privilege can run useradd

#### A user in linux can be normal user or system user

#### All users have a primary group and multiple secondary groups.

#### When invoked, useradd creates a new user account according to options specified on teh command line and the default values set in the /etc/default/useradd file.

#### useradd also reads /etc/login.defs which contains the config for shadow password suite such as expiration policy, user ID range etc

#### Default behaviour of useradd comamnd is to create a group with same name and id as username and user id and set this group as primary group of user.

#### Create a new user with below command. The command adds an entry to /etc/shadow, /etc/passwd, /etc/group and /etc/gshadow
* sudo useradd username

#### To set password of new user, run
* sudo passwd username

#### On most distros, useradd does not automatically create home directory for user. USer -m option to create this. The home directory by default is created in /home and gets contents of /etc/skel copied to it. These are .bash_logout, .bashrc and .profile files
* sudo useradd -m username

#### To create home directory anywhere else, run
* sudo useradd -m -d /opt/username username

#### Create user with specific user id
* sudo useradd -u 1500 username

#### Verify user's id with
* id -u username

#### Create user with group. This group should already exist
* sudo useradd -g users username

#### To verify user's GID, run
* id -gn username

#### To verify all groups a user belongs to
* id username

#### Add secondary groups to user with teh command
* sudo useradd -g users -G wheel, developers username

