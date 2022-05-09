# CSE15L Lab Report 3 (Week 6)

## Streamlining `ssh` Configuration

### `.ssh/config` File
The config file can be found at: `C:\Users\[User]\.ssh`. If the config does not exist, it must be made. The config after entering the three lines of code looks like this:

![configFile](images\configFile.png)

### `ssh` Command 
We can now log into the `ieng6` account using the new alias.

![sshCommand](images\scpCommand.png)

### `scp` Command
We can also use the alias to copy over files.

![scpCommand](images\scpCommand.png)

## Seting up Github Access From `ieng6`

### Where the Public Key is Stored on Github
On Github, there is a tab in the settings where you can store, add, or remove
`ssh` keys. 

![publicKeyGithub](images\publicKeyGithub.png)

### Where the Public/Private Key is Stored On User
The keys are located in the same location as the config file. The public key
is located in the `.pub` file while the private is in the other. 

![publicPrivateKeyUser](images\publicPrivateKeyUser.png)

### Running `git` Commands to Commit and Push a Change From `ieng6`
After adding the `ssh` key to Github, we can now push and commit changes from
the `ieng6` server directly to Github using git commands from the command line. 

![commandLineCommit](images\commandLineCommit.png)

### Link for the Commit
https://github.com/ni-chiu/markdown-parser2/commit/8cb7b78adc035e7dc28b680cab650e853bd8d26f

## Copy Whole Directories With `scp -r`

### Copying the markdown-parse Directory to the `ieng6` Account
To copy the whole directory into the `ieng6` account, we can use the command 
`scp -r ieng6:/markdown-parser-nichiu`.

![copyingWholeDirectory](images\copyingWholeDirectory.png)

### Logging in, Compiling, and Running the Tests for the Repository
After copying the directory over, we can now change our directory to the newly copied
directory, compile files, and run tests. This portion of testing was run through 
remote access through VSCode which is why there is no `ssh ieng6` command. 

![remoteTesting](images\remoteTesting.png)

### Copying the Whole Directory and Running the Tests in one Line 

We can achieve this by combining `scp`, `;`, and `ssh`, as shown by the screenshot below. 
The individual components are the previous commands used, only combined together into one line.
The one exception is that to avoid an error caused by mismatched java versions, we need to use 
a different line of code for the javac and java: 

```
/software/CSE/oracle-java-17/jdk-17.0.1/bin/javac
/software/CSE/oracle-java-17/jdk-17.0.1/bin/java
```
![oneLine1](images\oneLine1.png)

![oneLine2](images\oneLine2.png)
