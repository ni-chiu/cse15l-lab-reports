# CSE15L Lab Report 1 (Week 2)

This blog post is written as Lab Report 1 for CSE15L. This post will discuss remote access (as well as related topics like moving files between computers and setting SSH keys) and terve as a tutorial for logging into a course-specific account on ieng6. 

## Installing VScode
To install VSCode, I nagivated to the [Visual Studio Code site](https://code.visualstudio.com/download) and downloaded the version corresponding to my operating system (Windows). There are also versions for all other major operating systems.

![VSCode Download Page](images\VSCode_Download.png)

![VSCode Home Page](images\VSCode_Home_Page.png)

## Remotely Connecting
Since I am on Windows, I had to navigate to [this link](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) to install Open SSH on my machine. Then, in VSCode, I opened a terminal window from the Terminal tab and used the command:
<br>
$ ssh cs15lsp22---@ieng6.ucsd.edu

--- should be replaced by whatever your unique username is. When connecting for the first time, 'Yes' should also be selected when the terminal says 'Are you sure you want to continue connecting'. Lastly, the password will not show when being inputted so it is easier to copy-paste it from elsewhere.

![SSH Command and Login](images\SSH.png)

## Trying Some Commands
Below are a list of common UNIX commands and what they do:
* pwd : print working directory
* ls : list files

* cp : copy
* mv : move or rename
* cd : change directory
* mkdir : make directory
* rm : remove
* cat : view or create a file


## Moving Files with SCP

## Setting an SSH Key

## Optimizing Remote Running
