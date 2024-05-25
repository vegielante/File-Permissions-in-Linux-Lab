<h1>File Permissions in Linux</h1>




<h2>Scenario</h2>

<p align="center">

<img src="https://i.imgur.com/ajCewwu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<h2> Project Description</h2>
In this project, I'm going to demonstrate how to check and modify permissions using Linux Commands.
To help keep my organization's system secure, the research team decided to investigate and update the permissions of the files and directories under projects directory. In order to do this, I used a few Linux commands and followed the steps given to me by the research team.


<h2>Project Walkthrough</h2>

<p align="center">
Check file and directory details
 <br/>
<img src="https://i.imgur.com/fBKHz79.png" height="80%" width="80%"/>
 
 In the first and second lines, ***cd*** command allowed me to navigate the projects directory then I followed it with another command which is ***ls -la***; this command displayed the hidden files, permissions to files and directories. ls -la command output shows me the following:
A hidden file named ***.projects_x.txt***; hidden files start with a **period (.)** in their name.
A subdirectory named drafts
Project files that include: **project_k.txt, project_m.txt, project_r.txt, and project_t.txt**
<br />
<br />
<h2></h2>
<p align="center">
Describe the permissions string
<br/>
<img src="https://i.imgur.com/fBKHz79.png" height="80%" width="80%"/>
 
Permission string is a 10-character string that determines who is  authorized to access the files amongst the 3 types of owners: **user, group, and other.**
 Each character in the Permission string has its own representation.
<br />
- 1st character - can either be a ***d*** or a ***hyphen (-)***. If it starts with ***d***, it means that it is a Directory. If it starts with ***hyphen (-)***, it is a regular file. Based on the screenshot above, projects: **project_k.txt, project_m.txt, project_r.txt, and project_t.txt** are all files as well as the hidden file ***.project_x.txt***
- The characters ***(2nd-10th)*** indicate the **r = read, w = write, and x = execute**, as well as a hyphen (-) which basically means that the owner cannot access this particular permission/s.

Characters **2nd-4th** are permissions to User.

Characters **5th-7th** are permissions to Group.

Characters **8th-10th** are permissions to Other.

For example, ***project_m.txt*** file permissions are **-rw-r - - - - -** (without the spaces). The string starts with (-) which means that this project is a regular file. The 2nd and 5th characters are r, which means that user and group have read permissions. The 3rd character is w which indicates that user has write permission. 8th-10th characters are hyphens (-) indicating that other have no permissions at all for this project.
<br />
<br />
<h2></h2>
<p align="center">
Change file permission
<br />
 
The organization doesn’t allow other to have write access to any files. Because of this, **project_k.txt** permission for other should be modified since it is the only file that has write access.
Screenshot below is the linux command I used to modify the project_k.txt and underneath it shows the output of the command.
<br/>
<p align="center">
<img src="https://i.imgur.com/KKNTXtT.png" height="80%" width="80%" />
<br />
 
 ***chmod*** command is often used to change permissions on files and directories. When using chmod, it requires two arguments in order to use the command. The first argument indicates how to change permissions, and the second argument indicates the files or directory that you want to change permissions for. I also used the **ls -la** command to verify if the chmod command that I wrote is correct.  
<br />
<br />
<h2></h2>
<p align="center">
Change file permissions on a hidden file
<br />
 
The research team has archived **.project_x.txt** and they want this file to not have write permissions for anyone, but the user and group should have a read permission.
Screenshot below shows the Linux command I used to modify this specific task.
<br />
<p align="center">
<img src="https://i.imgur.com/Yzz2nG9.png" height="80%" width="80%" />
<br />
 
The Linux commands I wrote were shown in the first 2 lines. Since the research team wants to remove the write permissions for both user and group **u-w and g-w** is followed by **chmod**.
They also wanted the group to have a read permission so I added **g+r** at the end of the command action.
<br />
<br />
<h2></h2>
<p align="center">
Change directory permissions
<br />

All the files and directories in the projects directory belong to researcher2. In this scenario, Only researcher2 should be allowed to access the drafts directory (7th line) and its contents. 
Screenshot below shows the Linux command I used to change the directory permission on this step.
<br/>
<p align="center">
<img src= "https://i.imgur.com/b5uF7rg.png" height="80%" width="80%" />
<br />

Since ***drafts*** were executable by the group, I used the **chmod** command with **g-x** to remove their execute permission. No additional permissions that need to be changed to the command since the **user** has full access to the drafts directory.
<br />
<br />
<h2></h2>
<p align="center">
Summary
<br />
 
The task given to me by my organization was to examine existing permissions and determine if the permissions matched the authorization given. I started the task by using the Linux command **cd** to navigate the **projects directory** then I used **ls -la** command to display hidden files, permissions and directories under projects directory.  I used the **chmod** command to modify the permissions in the files shown and directories.









<!--
Step-by-Step Instructions
https://i.imgur.com/GFoSzyx.png
https://i.imgur.com/TXiAETF.png
--!>
