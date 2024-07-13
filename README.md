# Linux Command Reference

## Basic Commands

### Check Current Directory
- `pwd`: Displays the present working directory.

### Check Current User
- `whoami`: Outputs the current logged-in user's name.

### Check Date and Time
- `date`: Displays the current date and time.
- `date +%D`: Custom format to display the date.

### List Files and Directories
- `ls`: Lists files and directories in the current directory.
- `ls -lt`: Lists files with details, sorted by modification time.
- `ls -ltr`: Lists files with details, sorted by modification time with the latest at the bottom.
- `ls -lh`: Lists files with human-readable file sizes.

### Read Files
- `cat filename`: Outputs the contents of a file.
- `less filename`: Opens the file in a viewer, allowing navigation with:
  - `/word`: Search for a word
  - `n`: Next occurrence
  - `Ctrl + G`: Bottom of the file
  - `f`: Top of the file
  - `q`: Quit
- `more filename`: Reads file page by page.

## File Management

### Create and Remove Files
- `touch filename`: Creates a new file.
- `rm filename`: Removes a file.

### Edit Files
- `vi filename`: Opens the file in `vi` editor:
  - `i`: Insert mode
  - `Esc` and `:wq`: Save and quit
- `nano filename`: Opens the file in `nano` editor:
  - Use control commands for various operations.

### Manage Directories
- `mkdir foldername`: Creates a new directory.
- `rmdir foldername`: Deletes an empty directory.
- `cd foldername/`: Changes to a specified directory.
- `cd ..`: Moves back one directory.
- `cd /`: Moves to the root directory.

## Path Types
- **Absolute Path:** Starts from the root directory (e.g., `cd /home/docker`).
- **Relative Path:** Based on the current directory (e.g., `cd newfolder/newfolder2`).

## Copy and Move Files
- `cp filename /dest/path`: Copies a file to a specified directory.
- `cp ../filename .`: Copies a file from the previous directory to the current directory.
- `cp filename newfilename`: Copies a file within the same directory.
- `mv filename /dest/path`: Moves a file to a specified directory.
- `mv filename newfileName`: Renames a file.

## Display File Content
- `head -5 filename`: Shows the first 5 lines of a file.
- `tail -5 filename`: Shows the last 5 lines of a file.
- `sort filename`: Sorts file content.
- `sort -r filename`: Sorts file content in reverse order.
- `sort sortdemo.txt | uniq`: Displays unique data from a sorted file.
- `split -l 3 file`: Splits a file into smaller files with 3 lines each.
- `grep "word" filename`: Searches for a word in a file.
- `egrep "word1|word2" filename`: Searches for multiple words in a file.
- `ls new*`: Lists files starting with "new".
- `ls *.txt`: Lists files ending with ".txt".

## Create Multiple Files
- `touch file{1..10}`: Creates 10 files named file1 to file10.

## Shuffle and Count Lines
- `shuf filename`: Shuffles the lines in a file.
- `wc -l filename`: Counts the number of lines in a file.

## Compare Files
- `cmp file1 file2`: Checks if two files are identical.
- `diff -u file1 file2`: Compares and displays differences between two files.

## Find Files
- `find /path/ -name filename`: Finds a file by name.
- `locate filename`: Finds a file using a cached database (run `updatedb` first).

## Command History
- `history`: Shows the history of commands used.
- `history | grep sort`: Filters history for commands containing "sort".

## Command Help
- `help`: Displays help for built-in commands.
- `ls --help`: Shows help for the `ls` command.
- `man commandName`: Displays the manual page for a command.

## Compress and Decompress Files
- `zip myfiles.zip file1 file2`: Compresses multiple files into one zip file.
- `unzip myfiles.zip`: Uncompresses a zip file.
- `unzip -l myfiles.zip`: Lists files in a zip file without uncompressing.
- `gzip -k filename`: Compresses a file, keeping the original.
- `gzip -d filename` or `gunzip filename`: Decompresses a file.
- `tar -czf newname.gz filename`: Compresses a directory.

## Download Files
- `wget URL_OF_FILE`: Downloads a file from the internet.
- `wget -O opt_file.txt URL_OF_FILE`: Downloads a file and saves it with a specified name.

## Make API Calls
- `curl api`: Makes an API call.

## Package Management
- `apt` or `yum/dnf`: Installs applications.
- `dpkg -l | grep nginx`: Checks if an application is installed.
- `dpkg -l`: Lists all installed applications.
- `apt search <package_name>`: Lists available packages to install.

## Service Management
- `systemctl start/stop/status service_name`: Manages services.
- `systemctl list-units --type=service --all`: Lists all services.

## Environment Variables
- `printenv`: Lists all environment variables.

## Text Processing
- `cut -c1-2 file1`: Prints the first 2 characters of each line.
- `sed -n '3p' file1`: Displays the 3rd line of a file.
- `sed -i 's/MP/HR/g' filename`: Replaces all occurrences of "MP" with "HR" in a file.
- `tr '[:lower:]' '[:upper:]' < file2`: Converts text from lowercase to uppercase.
- `truncate -s 50M file2`: Sets the size of a file to 50MB.
- `echo "ABCDE" | fold -w1`: Prints each character on a new line.

## Remote Server Access
- `ssh user@hostname`: Connects to a remote server.
- `scp file user@hostname:/tmp/`: Copies a file to a remote server.

## Permissions Management
- `ls -ltr`: Checks file permissions.
- `chmod a+rwx file.txt`: Modifies file permissions.
- `chown root file.txt`: Changes file ownership.
- `chgrp groupname filename`: Changes group ownership.

## Memory and System Info
- `free -th`: Checks memory usage.
- `top`: Displays CPU and memory utilization.
- `du foldername`: Checks disk utilization.
- `df -h`: Checks filesystem and disk space.
- `hostname`: Checks the hostname.
- `lscpu`: Displays CPU information.
- `arch`: Displays system architecture.
- `lsblk`: Lists storage devices.
- `uname -a`: Displays OS information.

## Process Management
- `ps -ef | grep nginx`: Checks if a process is running.
- `pgrep nginx`: Gets the PID of a process.
- `kill -9 pid`: Kills a process by PID.
- `pkill nginx`: Kills a process by name.
- `jobs`: Lists jobs.
- `bg`: Resumes a job in the background.
- `fg`: Resumes a job in the foreground.
- `nohup ./script >/dev/null &`: Runs a script in the background.

## Network Information
- `ifconfig`: Checks IP address.
- `ping www.google.com`: Checks connectivity to a server.
- `telnet IP Port`: Checks if an IP:PORT is accessible.
- `netstat -putan | grep 3000`: Checks if a port is open.
- `traceroute`: Checks network path to a website.

## System Reboot
- `reboot`: Restarts the system.

## User Management
- `useradd`: Creates a new user.
- `id username`: Checks user ID.
- `passwd username`: Sets or changes user password.
- `groupadd grpname`: Creates a group.
- `cat /etc/group`: Checks group file data.
- `usermod -G grpname username`: Adds a user to a group.
