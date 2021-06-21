## Don't use spaces. Use the underscore.
`pwd` means present working directory. Exclamation point is called a bang (means run command again). A pound sign followed by an exclamation #! is called a Shebang. 
There are 3 sets of permissions: owner, group, and other. When reading a file ex 1: -rw-r--r student student   This is a file and not a directory. A directory will begin with a "d."
This means that the owner (student) of the file or directory has read and write permissions, but not execute. The group name (student) has read permission but not write or execute. Every other user has read permiss but not execute. Full permiss have rwe. The chown command can change these permissions.
### the mv command
1. Renames a file 2. Moves a group of files. When moving to a nonexisting file, the old file is deleted and new file with new name is created. ex 1: there are 4 files A,B,C,D -> `mv` A to "corn.txt"   Sys will ask for confirmation before erasing file. There are still 4 files B,C,D,corn.txt  If moving to an existing file, it is overwritten and old file is erased
ex 2: 4 files and 2 have text. B contains "text in here", C ,D , corn.txt "corn text" -> `mv` corn.txt B -> `cat` B "corn text", C , D  There is now 3 files, corn.txt is gone. Using option -i will prompt confirmation before erasing. Using -f will force the overwrite if the file has weak overwrite protection. -n (no-clobber) prevents existing file from being overwrittens like nothing happened. -b creates backup of exisitng file with tilde ~ appended. 
ex 3: 4 files B,C,D, corn.txt (the files have text in them like before)-> `mv -b corn.txt B` -> `ls` B, B~,C,D   
### other commands
`df` Means disk free. Shows amount of free disk space and the file systems that have been mounted. Mounted- the directory in which the file sys appears.
`free`- provides info on amount of physical and swap memory    `grep`- (Globally search for Regular Expression and Print out) searches file for specified patterns. Basically Ctrl+f  `ls -la` is to list all files and directories
`apt` installs, updates, removes Deb packages. Deb is the installation package format for all Debian based distributions. Debian is the oldest operating system in Linux and distributes free and open-source software. `gdebi` is used to install local Deb packages. It will install and resolve issues when downloading a package. `dpkg` also installs Deb packages, however it will not resolve and dependency issues. Dependency- when one package relies on another package to work. Helps reduce disk usage.
`export`- When new shell is opened, environment variables are set. If they are changed (EX walk= "2mi" or Dog=fluffy), the shell can't tell. `export` updates the shell with the new variables.By itself the command shows all exported variables.   `ssh`- creates secure connection to remote machine, allows transfer of files without interference, and allows commands to be executed on the remote machine.
`scp`- allows files to be copied between one or two remote hosts. Works like `ssh`.  `rsync`- versatile copying tool. Copies files over secured path, famous for its delta-transfer algorithim (send only the difference in data from source files to existing files at destination).
`crontab`- opens the cron table. This is the list of tasks scheduled to run at intervals on the system. The daemon that reads the cron tab and executes the commands is called the cron. daemon- program that runs in the background without user interaction.
`ls`- lists all files and directorys. There are many options to change what `ls` shows. Ex: `lsof` lists all open files. `ls -l` or `ls -la` will list all contents in a table format. This can show permissions for files/directories and can be changed with `chown` & `chmod`.
`groups`- shows which groups the current user is a part of. Can enter name of another user and see those groups as well. Username will be followed by a : and then the groups are listed.
### git command
`Git` is a massivly useful tool with many many many MANY command options. The basics are that `git` is used to work with many people on one project. It creates copies of files that each person can use, change, and return to original file. One file can be shared across multiple servers and all users can see the changed data. It tracks changes at any point in time so anyone can return to the file in a previous point. `Git` works with the websit github to create repositories (repos). They are containers for projects tracked by `git`. Repos can be local, only being available on your own system. Or they can be remote which is how multiple people can work on the same project. 
1. `git init` starts git file for git to track. `git status` checks on status of file. Text will appear in red for untracked file. This helps keep track of changes made to which files. 
2. `git add` + name of file to specify what is being added. Text will turn green and user is told there are changes to be committed.
3. `git commit -m "message about what the file is; why this is committed`   `git log` will show what commits were made, what time, and message   `git push` will push data to specified area. In this case, to the github account.  `git pull` can be used to pull new info from account to user server.
### Source Command
`source` also can be just a dot . - read and execute a file. The difference between sourcing a script and executing is that `source` executes the script in the current enbironment. Trying to execute a script in a different environment (child-like shell or process) will not work. The script must be sourced. `source` owrk