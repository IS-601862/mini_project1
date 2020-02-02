# Linux Basics and VI editor
This section explains commands and gives example(s) usage for use [VI](https://en.wikipedia.org/wiki/Vi) to create and edit files on Linux and the basic commands that you need to manage the file system.

## Questions to answer: What is it? Why do you do it? How do you do it?

 - cd
- mkdir
- cp
- pwd
- mv
- rm
- history
- Home directory and ~
- file paths in linux
- Using the tab key to complete file paths
- Using up and down arrow for history

----

## Linux basics

Linux, files are ordered in a tree structure starting with the root directory.

This root directory can be considered as the start of the file system, and it further branches out various other subdirectories. The root is denoted with a forward slash '/'.

A general tree file system on your UNIX may look like this.

![linux tree](/images/linuxtree.png)


### Present Working Directory
The directory that you are currently browsing is called the Present working directory. You log on to the home directory when you boot your PC. If you want to determine the directory you are presently working on, use the command -

```linux
pwd
```

![pwd and home](/images/pwd.png)

pwd command stands for **print working directory**

Above figure shows that /home/akmalh is the directory we are currently working on. '~' symbol here means we are in the user home directory. Each user in linux system has own home directory and this thilde symbol is the shortcut to refer that


### Changing Directories
If you want to change your current directory use the **'cd'** command.

```linux
cd /tmp
```
Consider the following example.

![cd command](/images/cd.png)

Here, we moved from directory /tmp to /bin to /usr and then back to /tmp.

Navigating to home directory
If you want to navigate to the home directory, then type **cd**.

    cd

You can also use the cd ~ command.

![cd command](/images/cdhome.png)
    
    cd ~

### Moving to root directory
The root of the file system in Linux is denoted by '/'. Similar to  'c:\' in Windows.

Note: In Windows, you use backward slash "\" while in UNIX/Linux, forward slash is used "/"

Type 'cd /' to move to the root directory.

    cd /


TIP: Do not forget space between cd and /. Otherwise, you will get an error.

### Navigating through multiple directories
You can navigate through multiple directories at the same time by specifying its complete path.

Example: If you want to move the /cpu directory under /dev, we do not need to break this operation in two parts.

Instead, we can type '/dev/cpu' to reach the directory directly.

    cd /dev/cpu

Moving up one directory level
For navigating up one directory level, try.

    cd ..

Here by using the 'cd ..' command, we have moved up one directory from '/dev/cpu' to '/dev'.

Then by again using the same command, we have jumped from '/dev' to '/' root directory.

### Relative and Absolute Paths
A path in computing is the address of a file or folder.

Example - In Windows
```cmd
C:\documentsandsettings\user\downloads
```
In Linux
```linux
/home/user/downloads
```

There are two kinds of paths:

1. Absolute Path:

Let's say you have to browse the images stored in the Pictures directory of the home folder 'user'.

The absolute file path of Pictures directory **/home/guru99/Pictures**

To navigate to this directory, you can use the command.

    cd /home/user/Pictures

This is called absolute path as you are specifying the full path to reach the file.

2. Relative Path:

The Relative path comes in handy when you have to browse another subdirectory within a given directory.

It saves you from the effort to type complete paths all the time.

Suppose you are currently in your Home directory. You want to navigate to the Downloads directory.

You do no need to type the absolute path

    cd /home/user/Downloads

Instead, you can simply type 'cd Downloads' and you would navigate to the Downloads directory as you are already present within the '/home/user' directory.

    cd Downloads

This way you do not have to specify the complete path to reach a specific location within the same directory in the file system.


### Deleting Files
The 'rm' command removes files from the system without confirmation.

To remove a file use syntax -

    rm filename

### Moving and Re-naming files
To move a file, use the command.

    mv filename new_file_location

Suppose we want to move the file "sample2" to location /home/user/Documents. Executing the command

    mv sample2 /home/user/Documents

mv command needs super user permission. Currently, we are executing the command as a standard user. Hence we get the above error. To overcome the error use command.

    sudo command_you_want_to_execute

Sudo program allows regular users to run programs with the security privileges of the superuser or root.

Sudo command will ask for password authentication. Though, you do not need to know the root password. You can supply your own password. After authentication, the system will invoke the requested command.

Sudo maintains a log of each command run. System administrators can trackback the person responsible for undesirable changes in the system.

    user@VirtualBox:~$ sudo mv sample2 /home/user/Documents 
    [sudo] password for user: ****
    user@VirtualBox:~$ 

**For renaming file:**

    mv filename newfilename

NOTE: By default, the password you entered for sudo is retained for 15 minutes per terminal. This eliminates the need of entering the password time and again.

You only need root/sudo privileges, only if the command involves files or directories not owned by the user or group running the commands

### Copying files
To copy a file, use the command.

    cp filename new_filename

Suppose we want to copy the file "sample2" to location /home/user/Documents with new name 'sampleNew'. Executing the command

    cp sample2 /home/user/Documents/sampleNew

### Directory Manipulations

Enough with File manipulations! Let's learn some directory commands.

Creating Directories

Directories can be created on a Linux operating system using the following command

    mkdir directoryname

This command will create a subdirectory in your present working directory, which is usually your "Home Directory".

For example,

    mkdir mydirectory

If you want to create a directory in a different location other than 'Home directory', you could use the following command -

    mkdir 

For example:

    mkdir /tmp/MUSIC

will create a directory 'Music' under '/tmp' directory

You can also create more than one directory at a time. 

    mkdir dir1 dir3 dir4






### Tips & Tricks

* In Linux terminal if you mistyped the command and you want to correct it or you want to execute the command that you typed before you can use **UP and DOWN arrow buttons** on your keyboard to browse the history of your command in current session.
* In the terminal (CLI) you can use the **TAB key** to autofill the file names (including directory files), but you need to enter the part of the file name until the Linux finds the unique file substring.
* You can also see all commands you used in the current sesson of your terminal with **history** command.
```linux
    history
```
![history](/images/history.png)

-----

### *VI editor*
vi is a screen-oriented text editor originally created for the Unix operating system. The portable subset of the behavior of vi and programs based on it, and the ex editor language supported within these programs, is described by (and thus standardized by) the Single Unix Specification and POSIX.[wiki](https://en.wikipedia.org/wiki/Vi)

The VI editor is the most popular and classic text editor in the Linux family. Below, are some reasons which make it a widely used editor –

1) It is available in almost all Linux Distributions

2) It works the same across different platforms and Distributions

3) It is user-friendly. Hence, millions of Linux users love it and use it for their editing needs

Nowadays, there are advanced versions of the vi editor available, and the most popular one is VIM which is Vi Improved. Some of the other ones are Elvis, Nvi, Nano, and Vile. It is wise to learn vi because it is feature-rich and offers endless possibilities to edit a file.

To work on VI editor, you need to understand its operation modes. They can be divided into two main parts.

### Command mode:
The vi editor opens in this mode, and it only understands commands
In this mode, you can, move the cursor and cut, copy, paste the text
This mode also saves the changes you have made to the file
Commands are case sensitive. You should use the right letter case.

![vi command mode](/images/vicmndmode.png)

### Insert mode:

This mode is for inserting text in the file.

You can switch to the Insert mode from the command mode  by pressing 'i' on the keyboard

![vi insert mode](/images/viinsertmode.png)
Once you are in Insert mode, any key would be taken as an input for the file on which you are currently working.

To return to the command mode and save the changes you have made you need to press the Esc key

### Starting the vi editor
To launch the VI Editor -Open the Terminal (CLI) and type
```unix
vi <filename_NEW> or <filename_EXISTING>
```

And if you specify an existing file, then the editor would open it for you to edit. Else, you can create a new file.

### The VI Editor

**VI Editing commands**

    i - Insert at cursor (goes into insert mode)
    a - Write after cursor (goes into insert mode)
    A - Write at the end of line (goes into insert mode)
    ESC - Terminate insert mode
    u - Undo last change
    U - Undo all changes to the entire line
    o - Open a new line (goes into insert mode)
    dd - Delete line
    3dd - Delete 3 lines.
    D - Delete contents of line after the cursor
    C - Delete contents of a line after the cursor and insert new text. Press ESC key to end insertion.
    dw - Delete word
    4dw - Delete 4 words
    cw - Change word
    x - Delete character at the cursor
    r - Replace character
    R - Overwrite characters from cursor onward
    s - Substitute one character under cursor continue to insert
    S - Substitute entire line and begin to insert at the beginning of the line
    ~ - Change case of individual character

*Note: You should be in the "command mode" to execute these commands. VI editor is case-sensitive so make sure you type the commands in the right letter-case.*

Make sure you press the right command otherwise you will end up making undesirable changes to the file. You can also enter the insert mode by pressing a, A, o, as required.

**Moving within a file**

    k - Move cursor up
    j - Move cursor down
    h - Move cursor left
    l - Move cursor right

*You need to be in the command mode to move within a file. The default keys for navigation are mentioned below else; You can also use the arrow keys on the keyboard.*

**Saving and Closing the file**

    Shift+zz - Save the file and quit
    :w - Save the file but keep it open
    :q - Quit without saving
    :wq - Save the file and quit

*You should be in the command mode to exit the editor and save changes to the file.*

![hello world](/images/visaveandquit.png)

### **The VI Editor Summary:**

The vi editor is the most popular and commonly used Linux text editor.

It is usually available in all Linux Distributions.

It works in two modes, Command and Insert

Command mode takes the user commands, and the Insert mode is for editing text

You should know the commands to work on your file easily
Learning to use this editor can benefit you in creating scripts and editing files.


### Reference

This tutorial is prepared based on [guru99.](https://www.guru99.com/)