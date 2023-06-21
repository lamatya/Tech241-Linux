## Linux Notes

Azure Week

Day 2


What command changes file permissions?

The chomd command. In Linux it controls who can access files, search directories and run the scripts using Linux'x chmod command. 

- chmod +rwx filename to add permissions
- chmod -rwx directoryname to remove permissions. 
- chmod +x filename to allow executable permissions.
- chmod -wx filename to take out write and  executable permissions.

r- read
w- write
x- execute

To change permissions on a file what must the end user be? (2 answers)

- be the owner or have the full user right (super user).


**Linux**

*Why Linux*

- Fast growing- its open source
- Dont have to pay for license. 
- less restart needed. 
- less expensive and popular on work desktop as its supports app. 
- DevOps uses Linux.its a clone of unix OS. unix is used in large frames whilst linux can be used on small frames. it is made up of karnel-core os. It has many libraries which relies on karnel. 

- Linux works on gitbash because when you install gitbash it downloads special feature which is running on the background which is why linux command works on gitbash.

**BASH**


What is Bash?
- BASH stands for Born Again SHell. path to bash shell-- /bin/bash

- It is a imporved verison of shell. 
- Shell- it is a software which provides interface to run the commands. There are multiple shells.

**(ps) command shows what processor your are running. hence it is helpful 

**command, -c ---> Clears the history 

*To navigate files and folders;*

- Get to home directory/folder - cd or cd ~
- To get to youe root directory/folder - cd /

**Linux Commands we need;**

1. ls - Lists files and directories

2. cd - change directory

3. pwd - prints the current working directory

4. mkdir - Creates a new directory

5. cp - copies files and directories

6. mv - moves or renames files and directories.

7. cat - displays the content of the file. 

8. history - shows all the commands used

9. ls -a - shows hidden files and directories

10. ls -l shows details of each files and directories.

11. curl - used to make requests to URLs to retrive data and --output is used to output the file where the data will be downloaded and stored

12. file -determines the file and its contents and provides information about the format,etc.

13. rm -r - Removes the file or directories

14. touch - Creates a new file

15. nano - text editor 

16. cat -  shows the content of the files

17. nl - shows the contens in with line numbers.

18. head - shows/displays the first few lines/heading of a file

19. tail - shows/displays the last few lines/end of a file

20. uname -retrieve information about the system



**Task 2.8a: Research managing file ownership**

1. Why is managing file ownership important?

Managing file ownership is important for security, accountability, permission management, collaboration, and file organization. It helps to establish a structured and controlled environment that enhances data protection, teamwork and ensures efficient file management.


2. What is the command to view file ownership?

- ls -l 
or
- ls -la (shows hidden files)


3. What permissions are set when a user creates a file or directory? Who does file or directory belong to?

Permissions are set to defult for both file or directory. File or directory belongs to the owner/user who created it by defult. Both permission and owner can be modified. 


4. Why does the owner, by default, not receive X permissions when they create a file?

By default, the owner does not receive X permissions when they create a file to ensure better security and prevent from files to be excuted.


5. What command is used to change the owner of a file or directory?

chown command is used to change the owner of a file or directory.



**Task 2.8b: Research managing file permissions**

1. Does being the owner of a file mean you have full permissions on that file? Explain.

Being the owner of a file gives you certain permissions and control over that file, but it does not necessarily imply having full permissions on the file. The permissions of a file determine who can perform specific actions on it, such as reading, writing, or executing.

2. If you give permissions to the User entity, what does this mean?

User entity means that it gives the user account specific permission allowing the user to perform specific actions or have access to certain resources within the system.


3. If you give permissions to the Group entity, what does this mean?

Group entity means it gives the group of user accounts  who shares a common group membership/platform specific access/permission which ensures consistent access control for users with similar roles. 


4. If you give permissions to the Other entity, what does this mean?

Other entity means giving specific access rights to all users who are not the owner or part of the group associated with the file. It determines what actions can be performed on the file by users outside the owner and group categories.


5. You give the following permissions to a file: User permissions are read-only, Group permissions are read and write, Other permissions are read, write and execute. You are logged in as the user which is owner of the file. What permissions will you have on this file? Explain.

As the owner of the file, it will only allow read-only permissions to view the file's contents but will not be able to modify or delete it. 

6. Here is one line from the ls -l. Work everything you can about permissions on this file or directory.
-rwxr-xr-- 1 tcboony staff  123 Nov 25 18:36 keeprunning.sh

The given file or directory has specific permissions assigned to the user, group, and other entities. The user has read, write, and execute permissions, the group has read and execute permissions, and other have no permissions. The file size is 123 bytes, and it was last modified on November 25th at 18:36.



**Task 2.8c: Research managing file permissions using numeric values**

1. What numeric values are assigned to each permission?

- Read: 4

- Write: 2

- Execute: 1

- No permissions: 0


2. What can you with the values assign read + write permissions?

When you assign read + write permissions (numeric value 6) to a file or directory, it allows certain privileges to the entities specified in the permission settings. 

- Read the contents: Read permission allows you to view the contents of the file or directory. 

- Modify the contents: Write Permission allows you to modify the contents of a file or directory. You can edit the data stored within a file, add new content, or delete existing content.  

- Rename or move the file or directory: Write permission enables you to change the name of the file or directory or move it to a different location within the file.

- Change permissions: write permission also allows yot to modify the permissions associated with the file or directory. This includes changing the permission settings for yourself, the group, or others.

3. What value would assign read, write and execute permissions?

Read,  write and execute- numberic value 7 (4 + 2 + 1)

4. What value would assign read and execute permissions?

Read amd execute- numberic value 5 (4 + 1)

5. Often, a file or directory's mode/permissions are represented by 3 numbers. What do you think 644 would mean?

- The first digit, 6, represents the permissions for the owner of the file (Read, write and execute)

- The second digit, 4, represents the permissions for the group the file belongs to (Read only)

- The third digit, 4, represents the permissions for others (everyone else) who are not the owner or part of the group (read only)



**Task 2.8d: Research changing file permissions**

What command changes file permissions?

- The chomd command. 


To change permissions on a file what must the end user be? (2 answers)

- be the owner or have the full user right (super user).


Give examples of some different ways/syntaxes to set permissions on a new file (named testfile.txt) to:

a.  Set User to read, Group to read + write + execute, and Other to read and write only

- chmod u=r, g=rwx, o=rw testfile.txt


b.  Add execute permissions (to all entities)

- chmod g-w testfile.txt


c.  Take write permissions away from Group

- chmod 640 testfile.txt


d.  Use numeric values to give read + write access to User, read access to Group, and no access to Other.

- user- Read + write (6) Group- Read(4) Other-No access (0)

