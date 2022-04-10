# CSE15L Lab Report 1 (Week 2)

This blog post is written as Lab Report 1 for CSE15L. This post will discuss remote access (as well as related topics like moving files between computers and setting SSH keys) and serve as a tutorial for logging into a course-specific account on ieng6. 

## Installing VScode
To install VSCode, I nagivated to the [Visual Studio Code site](https://code.visualstudio.com/download) and downloaded the version corresponding to my operating system (Windows). There are also versions for all other major operating systems.

![VSCode Download Page](images\VSCode_Download.png)

![VSCode Home Page](images\VSCode_Home_Page.png)

## Remotely Connecting
Since I am on Windows, I had to navigate to [this link](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) to install Open SSH on my machine. Then, in VSCode, I opened a terminal window from the Terminal tab and used the command:
<br>
`$ ssh cs15lsp22---@ieng6.ucsd.edu`

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

In lab, I ran the 'cd' command which did not do anything because I did not give a specific directly to be changed to.

![cd](images\cd.png)

## Moving Files with SCP
To move a file from the client to server, you have to run the scp command from the client. In lab, I created a file called WhereAmI.java and compiled it. Then, I moved it from my computer to the ieng6 computers using the command:
<br>
`scp WhereAmI.java cs15lsp22---@ieng6.ucsd.edu:~/`

where --- was replaced by my username. After inputting my password, I was able to see the file in my home directly using the ls command.

![SCP](images\SCP.png)

## Setting an SSH Key
To set an SSH key, I generated public/private key pair using the command:
ssh-keygen -t ed25519. After saving the key, I logged into the ieng6 server and ran the command: `$ mkdir .ssh`

Then, after logging out, I ran the command: `$ scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys` where I used the username for my client username and the path I saw using the previous command. 

The image below shows me logging into the remote server without needing to input a password:
![SSH](images\SSH.png)

## Optimizing Remote Running
To optimize remote running, we can combine multiple commands into the same line using semicolons. We can also put commands in quotes after an ssh command to run them on the server after login. That means we can do local changes and immediately copy them to and run them on the remote server since we have already set up our SSH key. I used the command:

`$ ssh cs15lsp22afz@ieng6.ucsd.edu "javac WhereAmI.java ; java WhereAmI"`

![Optimize](images\Optimizing.png)

This command logs into the remote server, compiles the file, and runs it all in the same line. 

## End
Thank you for reading!