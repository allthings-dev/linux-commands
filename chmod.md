# chmod

#### The chmod command sets permissions for user, group and others respectively

#### The access levels are read(4), write(2) and execute(1) for both files and folders

#### The access levels are additive like 6 for read and write and 7 for r+w+x

#### R,w,x for files are intuitive

#### For folders, read means permission to list the folder's files, write means permission to add/remove files from a folder and execute means permission to "cd" into teh folder

#### Command to give rwx to user, r to group and no permission to others
* chmod 740 file2

#### Comamnd to recursively give permission
* chmod -R 740 folderA
