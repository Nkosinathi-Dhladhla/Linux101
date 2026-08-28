# Users and Groups

- There are three commands you can use to check who is logged into the computer:
- users, who, w

## /etc/passwd
- This file is used to check user information on the system. Despite the name, it does not contain users' actual passwords
 - The first column is the username.
 - The second column is the password replaced by 'x'
 - The third column is the user's unique identifier within the system
 - The fourth column is the unique identifier of the users primary group
 - The fifth column is the text field that provides additional information about the user's account such as the name, cell number etc
 - The sixth column is the user's home directory
 - The final column is the user's default shell

## /etc/group
- This file has four columns
  - The first column is the group name
  - The second column is for the group password
  - The third column is the group's unique identifier
  - The last column is a comma separated list of usernames of users that are members of the group
 
# File and Directory permissions
- Linux uses a specific permissions mechanism to ensure proper user access to files and directories. You can see these permissions by using ls -l
- Permissions are shown in the first column. E.g: drwxrwxr-x or lrwxrwxrwx
  - The first character indicates the type of the item. d for directory or l for symbolic links
  - Each of the next three blocks are indicated by three characters each. The first block of characters is the permissions for the owner of the file/directory.
  - The second permission block is for users of the same group as the one associated with the file
  - The final block is for other users.
  - The rwx represent read, write, and execute permissions
- If you want to change the permissions in a file directory use the chmod command
  There are two ways to specify permissions (Symbolic mode and Octal mode)
  - The format of symbolic mode is ugoa. E.g: Lets change the permissions for hello.txt
                                            - ls -l hello.txt
                                            - chmod g-w hello.txt
  - For the Octal command you need to know how to count an octal
<img width="1152" height="864" alt="image" src="https://github.com/user-attachments/assets/32df4935-a164-414e-b1ea-45c22a4bb1b6" />
- To change the owner of a directory, use chown command
- E.g: chown sally hello.txt
- or sudo chown sally hello.txt
- You could also use chgrp command

# Changing Users
- Some users are able to run commands as another user using the sudo command
- Previously we stated that passwords are stored in the shadow password file. That file is /etc/shadow
- To access a file that requires root level access such as a password file use sudo. e.g: sudo cat /etc/shadow
- If you want to perform a certain task as another user i.e sally then you would have to use the command: sudo -u sally cat /home/sally/sample.txt
- If you want to change to a different user to perform multiple commands then you can use the following: su sally

# Changing passwords
- use the command passwd then add your own password then the new password
