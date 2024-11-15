# Unix Commands with Explanations

## 1. File Management

| Command                  | Description                                      |
|--------------------------|--------------------------------------------------|
| `ls`                     | Lists files and directories in the current directory. |
| `cd [directory]`         | Changes the current directory to the specified one.   |
| `pwd`                    | Displays the current directory path.              |
| `mkdir [directory]`      | Creates a new directory.                          |
| `rmdir [directory]`      | Removes an empty directory.                       |
| `rm [file]`              | Deletes a file.                                   |
| `rm -r [directory]`      | Deletes a directory and its contents recursively. |
| `cp [source] [destination]` | Copies a file or directory to a new location.   |
| `mv [source] [destination]` | Moves or renames a file or directory.           |
| `touch [file]`           | Creates a new empty file or updates the timestamp of an existing file. |

## 2. File Viewing and Editing

| Command                  | Description                                      |
|--------------------------|--------------------------------------------------|
| `cat [file]`             | Displays the contents of a file.                 |
| `more [file]`            | Views file content one screen at a time.         |
| `less [file]`            | Similar to `more`, but allows backward navigation. |
| `head [file]`            | Shows the first 10 lines of a file (use `-n` to specify a number). |
| `tail [file]`            | Shows the last 10 lines of a file (use `-n` to specify a number). |
| `nano [file]`            | Opens a simple text editor.                      |
| `vim [file]`             | Opens a powerful text editor.                    |
| `grep [pattern] [file]`  | Searches for a pattern in a file.                |

## 3. File Permissions and Ownership

| Command                  | Description                                      |
|--------------------------|--------------------------------------------------|
| `chmod [permissions] [file]` | Changes the permissions of a file or directory. |
| `chown [user] [file]`    | Changes the owner of a file.                     |
| `chgrp [group] [file]`   | Changes the group ownership of a file.           |
| `umask`                  | Sets default permissions for new files and directories. |

## 4. Process Management

| Command                  | Description                                      |
|--------------------------|--------------------------------------------------|
| `ps`                     | Lists running processes.                         |
| `top`                    | Displays active processes and system resource usage. |
| `kill [PID]`             | Terminates a process by its process ID (PID).    |
| `killall [process_name]` | Kills all processes with a specific name.        |
| `bg`                     | Resumes a suspended job in the background.       |
| `fg`                     | Brings a background job to the foreground.       |

## 5. System Information

| Command                  | Description                                      |
|--------------------------|--------------------------------------------------|
| `uname`                  | Displays system information.                     |
| `uname -a`               | Shows detailed system information.               |
| `df`                     | Displays disk space usage.                       |
| `du`                     | Shows disk usage of files and directories.       |
| `free`                   | Displays memory usage information.               |
| `uptime`                 | Shows how long the system has been running.      |
| `who`                    | Lists users currently logged into the system.    |

## 6. Networking

| Command                  | Description                                      |
|--------------------------|--------------------------------------------------|
| `ping [host]`            | Tests connectivity to a host.                    |
| `ifconfig`               | Displays or configures network interfaces.       |
| `netstat`                | Shows network connections and routing tables.    |
| `curl [URL]`             | Transfers data from or to a server.              |
| `wget [URL]`             | Downloads files from a URL.                      |

## 7. Archiving and Compression

| Command                  | Description                                      |
|--------------------------|--------------------------------------------------|
| `tar -cvf archive.tar [file(s)]` | Creates an archive.                   |
| `tar -xvf archive.tar`   | Extracts an archive.                             |
| `gzip [file]`            | Compresses a file.                               |
| `gunzip [file.gz]`       | Decompresses a file.                             |
| `zip [archive.zip] [file(s)]` | Compresses files into a .zip archive.      |
| `unzip [archive.zip]`    | Extracts files from a .zip archive.              |

## 8. Other Common Commands

| Command                  | Description                                      |
|--------------------------|--------------------------------------------------|
| `history`                | Lists command history.                           |
| `clear`                  | Clears the terminal screen.                      |
| `echo [text]`            | Prints text to the screen.                       |
| `date`                   | Displays the current date and time.              |
| `alias [name]='[command]'` | Creates a shortcut for a command.             |
| `which [command]`        | Shows the path of a command’s executable.        |
