# LINUX COMMADS & NOTES

## NOTES
### What is Linux?
- Linux is often referred to as a Unix-like operating system because it follows many of the principles and design philosophies of Unix, but it is not a direct derivative of Unix.

- Unix was developed in the 1970s at AT&T Bell Labs, while Linux was created later, in 1991, by Linus Torvalds, who wanted to create an open-source, free operating system that followed Unix principles but was not based on Unix code.
  - Could think of linux as pasta. You can add anything to it but it is the base.
- Linux does not care about extensions. It will still know a jpg is a jpg even if you rename it.

## Linux Commands

- `uname` = Tells you the username.
- `--help` = Tells you everything you can do (commands)
- `uname -a` = Information in a bit more detail.
- `whoami` = Tell you who you're logged in as.
- `cat` = Shows the contents of the file/ thing you want to show.
- `ps -p $$` = Tells you what shell you are currently using. 
- `history` = Shows numbered list of last 500 commands you've used.
- `history -c` = Deletes history of commands.
- `!12` = Runs the command form that history number.  
- `ls` = Checks what files and folders are in the current directory.
- `ls -a` = Shows hidden files and folders in the directory. 
- `ls -la` = Shows permisssions (long format and hidden files/ folders)
- `curl followed by url --output name of destination file` = Generic downloading.
- `wget` = Used to download files and folders (better than curl)
- `cp` = Copy a file. Need to specify the file and where to copy to.
- `rm` = Remove something. Stater the file after the rm command. 
- `mkdir` = Creates a directory (folder).
- `rm -r` = Removes a directory (deletes content in directory and then removes directory).
- `vim` = Edit the contents of a file. State the file you are eiting. 
- `touch` = creates a file
- `head -` = Gives top content of file () 
- `tail -` = Bottom content of file.
- `nl` = numbers lines of content in file. 
- `cat chickenjoke.txt | grep chicken` = Will search for string in file and print the string (highlighted). 
- `sudo apt-install` = sudo "Super user do" allows you to be super user for task.
- `sudo apt update -y` =  Updates all installed packages without asking for confirmation (downloads new packages but doesn't install. It just enables apt install to know what you are asking to install when you do).
- `sudo apt upgrade -y` = upgrades all installed packages to the latest versions (❌Be careful—it upgrades everything without letting you review changes!)
- `cd ~` = Moves to home directory.
- `pwd` = Prints working directory.
- `cd /` = Moves to root directory.
- `sudo su` = Changes to root user (to leave root user = exit)
- `mv followed by file name and location` = moves file to that location.
- `man` = Tells you how programs work.
- `sudo systemctl status` = Checks the status of the program.
- `chmod` = Changes the permissions of a file (when followed by the permission number. e.g. 400 = read only)
- `chown` = Changes the owner of the file.
- `kill` = Terminates all running processes by its PID (Process ID)
- `df` = Shows disk space usage on all mounted file systems.
- `free` = Shows memory usage (RAM and swap space).
- `find` = Searches for files and directories based on criteria like name, type, or size.
- `tar -xzvf` = Used to compress or extract files. (tar -xzvf lemons.tar.gz = extracts the contents of lemons.tar.gz) 
- `ssh` = Securely connects to remote servers or systems via the command line.
- `scp` = Securely copies files between local and remote systems (scp file.txt user@remote:/path/to/destination (Copies file.txt to a remote system)).
- `rsync -av` = Efficiently syncs files and directories between two locations (rsync -av source/ destination/ (Syncs contents from source to destination)).
- `iptables` = Configures firewall rules to control network traffic.
- `echo` = Repeats the content.
- `echo $` = Prints the variable.

## TASK: Research the following topics/concepts/commands in Linux/Bash

### How can we set a variable in BASH?
- In Bash, you can set a variable by assigning a value to a name without spaces around the equal sign (=).
- You can then display that variable using echo $name
  - E.g. `name="John"`
    - `echo $name`
### What are environment variables?
- Environment variables are dynamic values that influence the behavior of processes and applications in an operating system. They provide important configuration settings and can define system behavior, user preferences, or application-specific settings.
- **Purpose of Environment Variables:**
  1. Configuration Management:
     - Environment variables help manage system and application configurations, such as the directories where executables are stored or the system's locale settings.
  2. Process Control:
     - These variables affect how processes are executed, often defining paths, user settings, and more. They help ensure the right environment for software to run properly.
  3. Global Availability:
     - Environment variables are globally accessible to processes across the system, making them an efficient way to store and share configuration data.
### How can we set one?
- To set an environment variable in Linux, use the export command in the shell.
  - `export VAR_NAME="value"`
    - E.g. `export MY_VAR="Hello World"`

### How can you make an environment variable **persistent**?
- To make an environment variable persistent (i.e., available across sessions), you need to add it to a configuration file that is executed when a new session starts.
  - Open the configuration file (e.g., ~/.bashrc, ~/.bash_profile, or /etc/environment for system-wide variables).
  - Add the export command to define the environment variable.
  - e.g.
    - `echo 'export MY_VAR="Persistent Value"' >> ~/.bashrc`
    - `source ~/.bashrc`
  - This ensures that MY_VAR  is set every time a new terminal session is opened.

### What is a process?
- A process is an instance of a running program. It includes the program's code, its current activity, and the resources (such as memory and CPU) it is using.
- Every time you run a program, the operating system creates a process to manage its execution.
### How can we see running processes?
- You can see the list of running processes using the `ps` (shows snapshot of current processes), `top` (Displays real-time system resource usage and running processes.), or `htop` (An interactive version of top with a user-friendly interface.) commands.
### What are child processes?
- Child processes are processes created by other processes (called parent processes). When a process spawns or creates another process, the new process is called a child process.
- In Linux, every process has a unique Process ID (PID), and the child process will have a unique PID, while the parent process’s PID is stored as the PPID (Parent Process ID) of the child.
### How can you run a process in the background, rather than the foreground?
- To run a process in the background, you can append an & symbol to the command, or you can use Ctrl + Z to suspend the process and then run bg to send it to the background.
  - `command &`
    - e.g. `sleep 100 &`    
### How can you end a process?
To terminate or stop a process, you can use the `kill` command.
### Explaining the linux permission system:
- Linux uses a permission system to control access to files and directories. It defines who can read, write, or execute a file. Each file or directory has associated permissions for the owner, the user, and the group.
### Shorthand permission system (numbers):
  - File permissions are represented by a 3 digit number. Each permission is given a numerical value:
    - **Read** (r) = 4
    - **Write** (w) = 2
    - **Execute** (x) = 1
  - By adding the values together you can represent the permissions for each category. 
  - There are 3 categories:
    1. Owner - user who owns the file or directory.
    2. Group - Each file or directory belongs to a group. A group is a collection of users.
    3. Others - Others represent all users who are not the owner and do not belong to the file's group.
### How can you change the permissions on a file?
- `chmod 755 lemons.txt` = Changes the permissions to rwxr-xr-x
  - The dash means that group doesn't have that access.
  - Owner = Can Read, Write and Execute the file.
  - Group = Can Read and Execute the file.
  - Others = Can Read and Execute the file.
- `chmod 400 lemons.txt` = Changes the permissions to r--------

