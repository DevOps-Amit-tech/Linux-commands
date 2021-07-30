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
| rm |	rm \<file\>	| Delete a file
|  | rm -r \<dir\> |	Delete empty/non-empty directories recursively.
|  | rm -f \<file\>	| Prompts error while deleting non-existent file/directory. Use -f to suppress such prompts

#### MANAGE FILES/DIRECTORIES
Command	| Usage	| Description
------- | ----- | -----------
cd	| cd | /path/to/directory	Change directory
|  |	cd  (or)  cd ~ 	| Navigate to home directory
|  |	cd /	| Move to root directory
|  |	cd ..	| Navigating up one directory level (Ex: If you are in /usr/bin folder then typing cd .. command will navigate to /usr folder)
cp |	cp \<file1\> \<file2\>	| Makes a copy of a file
|  |	cp -p \<file1\> \<file2\> |	Copy file by preserving time stamp.
|  | cp -i \<file1\> \<file2\>	| cp and mv commands doesn’t prompt while overwriting an existing file. Use -i interactive option to enable prompt.
|  |	\cp \<file1\> \<file2\> |	Use a backward slash before the cp command to force cp command to overwrite without confirmation 
|  |	cp \<file\> \<dir\> |	Copy file to a directory
|  |	cp -r \<dir1\> <dir2\>	| copy dir1 to dir2; create dir2 if it doesn't exist
mv	|	 | mv can be used to rename or move a file
|  |	mv \<file1\> \<file2\>	| Renames a file if moved in same dir (file1 disappears and file2 appears with same content as file1)
|  |	mv \<file1\> \<dir\>	| Move a file to a directory (mv command works like cut and paste)
diff	| diff \<file1\> \<file2\>	| compares two text files and shows the differences between them.
stat |  |	Display when a file was last accessed, modified, or changed.
 
#### FINDING FILES AND DIRECTORIES
Command	| Usage	| Description
------- | ----- | -----------
whereis	| whereis \<filename\>	| Shows possible locations of file.
which	| which \<filename/app\> |	Shows which app will be run by default. <br> **Ex:** which java
locate |	locate \<filename\>	| Find all instances of file using indexed database built from updatedb command. It searches a prebuilt database of files (updatedb) that needs to be updated regularly (once a day). Much faster than find, but if a file is deleted still will show matched, if the file image still exist in the database.
find	| find \<folder-path-in-which-to-find\> -options \<filename\>	| Find all instances of a files/directories in real system. <br> **Ex:1** find /home -name test.txt <br> Find a file named test.txt under /home directory. Use -iname option if you want to ignore case (ie., filename can contain upper/lower case letters) <br> **Ex:2** find / -type d -name "tomcat" <br> Find directory named tomcat under / path
 
#### LINKS
Link is similar to the shortcut concept that we have in windows. Imagine that you have files in D drive. You can create a shortcut on desktop so that you can simply click on shortcut and start accessing the files. 
There are two types of links available.
-  Soft link
-  Hard link
##### 1. Soft link:  (Shortcut file)
With soft link you can use the shortcut to access data as long as the original data is present.
Syntax:	ln -s {source-filename} {symbolic-filename}

**Ex:**  To create a soft link named file2 for file1 (both in the current directory). Whatever content present file1, the same content you can see via file2.
 
    ln -s file1 file2
##### Advantage of soft link:
Suppose there are files which you don’t want to give direct access to some users. In that case you can create a soft link out of original files and give soft link file access to other users. So even if the soft link file gets deleted, the original data will still remain. But if the original data itself is deleted then the soft link cannot do anything.

##### 2. Hard link:  (Backup file)
In case of hard link even though the original file is deleted still you can access the data via hard link file.
Syntax:	ln {source-filename} {symbolic-filename}
 
**Ex:** To create a hard link named file2 for file1 (both in the same directory)
 
    ln file1 file2
##### Difference between copy and hard link?
If you create a file1 with some content and copy it to file2 then it gets copied successfully. But if you make further modifications in file1 then those changes will not be reflected to file2. But with hard link all changes made to file1 will be reflected to file2.

#### ENVIRONMENT VARIABLES
Command	| Description | Example
------- | ----------- | ---------
echo $VARIABLE	| To display value of a variable | echo $PATH <br> To display value of PATH variable
env	| Displays all environment variables | 
VARIABLE_NAME=variable_value |	Create a new variable | VAR1=/usr/java/
unset VARIABLE_NAME |	Remove a variable	| unset VAR1
export Variable=value	| To set value of an environment variable |	export VAR1=/usr/tmp
 
#### I/O REDIRECTION
Redirection is a feature in Linux such that when executing a command, you can change the standard input/output devices.
**Ex:** With the help of redirection operators you can copy the output of any command(s), file(s) into a file.
Redirection	| Usage |	Description
----------- | ----- | ------------
Input Redirection \< |	command \< file |	**Ex:**  If you want to attach a file to email you can use the input re-direction operator in the following format. <br> mail -s "Subject" Recipient_MailID < Filename
Output Redirection \> |	command \> file	| Redirecting output to a file. Instead of displaying output on the cmd screen it will redirect to file. <br> **Ex:1**  ls -l \> file1 <br> **Ex:2**  data \> file1 <br> If you enter wrong command and redirect the output to file then it will display error on screen. Error will not be stored in file
Error redirection 2\>	|command 2\> file |	Redirects error message to the file you specify. <br> **Ex:1**  mkdir dir1/dir2/dir3 2\> file1 <br> It redirects the error message of mkdir to file1 <br> **Ex:2**  (data;cal) 2\> file1 <br> The error message will be redirected to file1 and the output of cal command will be displayed on screen.
Redirecting output and error &\> |	command &\> file |	If you want to store both output and error message in a file. <br> **Ex:** (data;cal) &\> file1
Appending \>\> |	command \>\> file | Append to file. If you do not want a file to be overwritten but want to add more content to an existing file
Redirecting  error without overriding | 2\>\> |	command 2\>\> file |	Redirects error message without overriding the contents of file. <br> Every time you execute 2\>, it will override the previous error message that is stored in file. But with 2\>\> it will append the error to the file.
Redirecting output and error without overriding &\>\> |	command &\>\> file |	Redirects both output and error without overriding the contents of file. Every time you execute &\>, it will override the previous output/error that is stored in file. But with &\>\> it will append the data to the file.
Heredoc \<\< |	Command \<\< delimiter <br> Any text/input <br> delimiter | \<\< is a type of redirection that allows you to pass multiple lines of input to a command. It reads the input until it finds a line containing the specified delimiter. Delimiter can be of any name, but note that you end with the same delimiter. <br> **Ex:** <br> wc -l << EOF <br> This is a <br> simple lookup program <br> EOF <br> o/p:  2
\| 	| command1 \| command2	| A pipe is a form of redirection that lets you run two or more commands, such that output of one command serves as input to the next command. <br> **Ex:** <br> head -5 file1 | tail -1 <br> head -5 file1 provides five lines and tail -1 provides last line that got from head command. So you will get fifth line from file1
 
#### METACHARACTERS
Symbol	| Description | Example
------ | ----------- | --------- 
&&	| AND conditional execution 	| command1 && command2
\|\| |	OR conditional execution	| command1 \|\| command2
; |	Command separator. Execute multiple commands at once such that each command is separated by a semi colon |	ls;date;cal
( )	| Groups commands |	date;cal \> file1 <br> Output of date command will be displayed on CMD and output of cal command will be stored in file1. When there are multiple commands which are given on same line then the redirection operator will work only on the immediate command not on previous commands. <br> If you want to redirect output of multiple commands to a file then ensure that the commands are enclosed in parenthesis <br> (date;cal) \> file1
$	| Variable substitution |	set name=Tom <br> Sets the variable name to Tom ; <br> echo $name <br> displays the value stored there
&	| Run a command in the background	|  |
| #	| Comment |	#This is a comment line
\ |	Avoid interpretation of meta-characters. Any meta-character immediately following backslash loses its special meaning. Sometimes we need to pass meta-characters to the command being run and do not want the shell to interpret them | echo Hello; world <br> **o/p:** <br> Hello <br> -bash: world command not found <br> <br> echo Hello\\; world <br> **o/p:** <br> Hello; world
‘ ‘	| All special characters between these quotes lose their special meaning | Consider an echo command that contains many special shell characters <br> echo \<-$1500.\*\*\>; <br> Putting a backslash in front of each special character is tedious and makes the line difficult to read. <br> echo \\<-\\$1500.\\*\\\*\\\>\\; <br> In that case simply Put a single quote (') at the beginning and at the end of the string. <br> echo '\<-$1500.\*\*\>;' 
“ “ |	Use double quotes when you want to display the real meaning of special variables. Double quotes take away the special meaning of all characters except the following. <br> $ Parameter Substitution <br> ` Backquotes <br> \\$ Literal Dollar Sign <br> \\´ Literal Backquote <br> \\” Embedded Doublequote <br> \\\\ Embedded Backslashes	| **Ex:1:** echo "Hostname=$HOSTNAME ;  Current User=`whoami` ; Message=\\$ is USD" <br> **o/p:** Hostname=dev-db ;  Current User=Tom ; Message=$ is USD <br> **Ex:2** echo "Hello   \\"World\\"" <br> **o/p:** Hello   "World
` `	| Anything in the back quote will be treated as a command and would be executed |	DATE=`date` <br> echo "Current Date: $DATE" <br> **o/p:** Current Date: Thu Jul  2 05:28:45 MST 2020
 
 
 
 
