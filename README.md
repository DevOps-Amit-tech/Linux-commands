Linux is an open source operating system developed by Linus Torvalds. Linux is just a kernel and a linux distribution makes it a usable operating system.
 
### 1. What is Kernel?
kernel is the core of the operating system that manages everything. Kernel is kind of a thing which interacts with your hardware and manages CPU resources, memory resources, processes on any computer.

### 2. What is Shell?
Shell is just a program, a friendly interface that translates your commands into some low-level calls to the kernel.

### 3. Simple Architecture:
![image](https://user-images.githubusercontent.com/43535914/126981748-d943ccd4-f290-4a13-a276-2fe6d7639650.png)

### 4. What are Linux Distros?
Distros nothing but distributions are specific group of software
In all linux distributions:
* Linux kernel is same (mostly). 
* Tools from GNU General public license is different.

The Linux operating system isn’t produced by a single organization. Few companies take the linux kernel and put up some modified version of their software on top of it and launch their own distributions of linux. They govern all the things like updation of the software, package repository, release of the new security patches etc.

Companies that are launching these distros are: Arch | Debian | Red hat | Slackware etc
Below mentioned are flavors of the above mentioned distributions
Debian	=>	Mint, kali, Ubuntu, Parrot, Deepin 
Red hat	=> 	Fedora, Centos (Community Enterprise Operating System), RHEL (Red Hat Enterprise Linux) 

### 5. File system hierarchy:
![image](https://user-images.githubusercontent.com/43535914/126982674-6caefcf4-bd46-4ee3-a702-09f86d7ebd7d.png)

Directory Name | Description
-------------- | --------------
/ | This is top level directory, also is called as ROOT directory. It is parent directory for all other directories.
/root | It is home directory for root user (super user). It provides working environment for root user 
/home |	Home directory. It provide working environment for all users other than root
/usr | By default softwares are installed in /usr directory 
(UNIX | Sharable Resources) 
/bin | It contains commands used by all users (Binary files)
/sbin | It contains commands used by only Super User(root) (Super user's binary files)
/var | Contains variable data like mails, log files

### 6. Terminal:
Terminal or command line or command prompt is basically a text interface to your computer. It allows us to send simple text commands to our computer to do things like navigate through a directory, copy a file, etc.

![image](https://user-images.githubusercontent.com/43535914/126983919-41650416-3a27-4641-ba95-7c725a9ebe24.png)

**\#** prompt indicates root user whereas **$** prompt indicates other users.

#### Below are few terminal shortcuts:
Command | Description
------- | --------------
ctrl+Alt+T |	Open terminal
ctrl+c | Stop the current command execution
TAB key |	To auto complete file or folder names
ctrl+a	| move cursor to beginning of line
ctrl+f	| move cursor to end of line
clear (or) ctrl+l	| To clear the terminal screen.
exit | close the terminal or logout of current session.
Up and Down arrow keys | To cycle through recently used commands in the terminal.

### 7. Commands in linux:
Linux commands are simply programs which are executed by the shell. In linux there are thousands of commands. Sometimes the command which you are executing may not be available in your OS. In that case download & install required package from respective repository (like apt, yum) and then execute.

**Ex:**
"command not found" error while executing tree command
tree is a command which is available in tree package. Download tree package and then execute that command

### 8. Installing softwares/packages:
In Linux, installation files are distributed as packages. A repository is a storage location from which your system retrieves and installs OS updates and applications. It is like a warehouse that consists of all packages.

**Ex:** Inorder to install a package in ubuntu
1. update the repository			                It will update/install dependent packages   apt-get update                    
2. Download & install the required package		It will install actual software             apt-get install <package-name>

Likewise "yum" is a repository for CentOS, "apk" is a repository for Alpine, etc
  
### 9.  Basic linux commands:
Command | Usage | Description
------- | ----- | ------------
date |  | Show the current date and time
cal	|	 | Show the month's calendar
history |	 | Displays a list of all recently used commands.
alias	|  | Defines shortcut for a long command
man	| man \<command name\> |	Displays a help page based on your search query
whatis |	whatis \<command name\> |	Displays brief description of command
echo	| echo “Hello” |	Display contents

### 10. File permissions:
**10.1. Types of permissions:**
Permission | Alphabetical notation | Numerical notation
---------- | --------------------- | ------------------
Read |	r |	4
Write	| w	| 2
Execute	| x	| 1
No permissions |  | 0   

"chmod" command is used to change the read, write, and execute permissions of a file/folder.

**Ex:**
##### Change permissions using numerical notation:
    chmod 755 <File/Folder name>
    Here 7, 5 and 5 individually represent permissions of User, Group and Others

##### Recursively apply permissions to all sub-folders and files recursively
    chmod -R 755 <Folder name>

##### Change permissions using alphabetical notation:
    +  is for giving permissions
    -  is for removing permissions
    =  is for replacing existing permissions
    chmod o+r file1       provide read permissions for others for file1
    chmod o+r+w+x file1   provide all permissions to others
    chmod u+x,g-w file1   add execute permission to owner and remove write permission to group
    chmod u=w file1       Replace existing permissions with new permissions (For suppose owner has rwx permissions and you want to replace with only write permission then you                             can use this)
  
**10.2. Types of ownership:** 
owner | Notation
----- | --------
User | u
Group | g
Others | o

"chown" command is used to change the user and/or group that owns a file/folder.

**Syntax:**  chown USER:GROUP <File/Folder name>
**Ex:**
    Both user & group:   chown dave:mary example.txt
    Only user:           chown dave: example.txt
    Only group:          chown :mary example.txt
  
### 11. Identifying file types:
A file type helps us in identifying the type of content that is saved in the file. Linux supports seven different types of files. 
Symbol	| Type of file
------- | ------------
\-	| Normal file
b	| Block special file (Hard disk or floppy disk)
c	| Character special file
s | local socket file
d	| Directory
l	| Link files
p | named pipe
  
When you list files or directories, you can identify a file type by viewing the first character as shown below.
![image](https://user-images.githubusercontent.com/43535914/126990264-4d9aecf8-0caa-434e-b436-b1fb07e52752.png)

  
## Linux-commands 
#### VIEW FILES/DIRECTORIES
Command |	Usage	| Description
------- | ----- | -----------
ls | ls |	lists all directories/files in the current terminal directory.
|  | ls -l	| lists files/folders in long table format (shows file/directory size, modified date & 		 time,ownership,permissions)
|  | ls –a	| List all the files including the hidden ones
|  | ls –t |	List the files sorted by last modified time
|  | ls -lrt  (or)  ll |	lists the contents of the directory with all the details, in reverse order of their modification time (older files will be displayed first).
pwd |  |	Show present working directory path.
tree	| tree \<dir_name\> | view hierarchical structure of a directory in tree format.
file | file \<filename\> | Determine the type of a file

#### READ A FILE
Command	| Usage	| Description
------- | ----- | -----------
cat	| cat \<filename\> | Read contents of the file
less | less \<filename\>	| Displays contents of file page by page. With cat command if the file is huge, it will quickly scroll everything and you can see only bottom part of file. To have file navigational control you can use less command. (give enter to navigate page, use “q” to come out of the command)
head | head \<filename\> | To view first 10 lines of a file.
|  | head -5 \<filename\> |	To view first 5 lines of file.
tail	| tail \<filename\>	| output the last 10 lines of file  

#### CREATE AND DELETE FILES/DIRECTORIES
Command	| Usage	| Description
------- | ----- | -----------
touch | touch \<filename\> | It is used to create empty file (0 bytes). It is also used to create, change and modify time stamps of a file.
vi | vi \<filename\> | Create a file using vi editor: <br> Press key “ i ” for insert mode as it allows you to enter text as needed. <br> Press **ESCAPE** key once you are done with file. <br>  **:wq** --- Save and quit (w for save and q for quit). <br>  **:q** --- quit without save if no changes are made to file. <br> **:q!** --- quit without saving changes made to a file
cat |	cat > [filename]	| Create a file and insert contents to that file on terminal. Press Ctrl+D to exit. If file already exists it overwrites.
|  | cat [file1] \> [file2] | Copy contents of one file to another. (\>  Can also be used to redirect the output of cat command to a file rather than standard output)
|  |cat [file1] \>\> [file2] | Instead of overwriting file2, it appends contents of file1 to file2 using redirection operator \>\>
|  |	cat \>\> file.txt << EOF <br> Insert multiple lines <br> EOF	| Write multiple lines from the command line.  <br> **Ex:** <br> cat << EOF <br> The current working directory is: $PWD <br> You are logged in as: $(whoami) <br> EOF
mkdir	| mkdir \<dir_name\> | Creates a directory
|  |	mkdir -p d1/d2/d3	| Create multiple sub directories (-p means Parent)
rmdir	| rmdir \<dir\>	| Removes empty directory
rm |	rm \<file\>	| Delete a file
|  | rm -r \<dir\> |	Delete empty/non-empty directories recursively.
|  | rm -f \<file\>	| Prompts error while deleting non-existent file/directory. Use -f to suppress such prompts


