\# Day 01 - Linux Basics \& EC2 Web Server Deployment 🚀



\## Introduction to Linux

Linux is a free, open-source operating system that originated as a project by \*\*Linus Torvalds\*\* in 1991. It is based on the foundations of UNIX, which was developed in the 1970s by Dennis Ritchie, who also created the C programming language.



\### Key Features of Linux

\- \*\*Multiple Distributions\*\*: Red Hat, Fedora, Ubuntu, Debian, Kali Linux, CentOS, Amazon Linux

\- \*\*Free and Open Source\*\*: Freely available for anyone to use, modify, and distribute

\- \*\*Security\*\*: Secure architecture with granular command-line control

\- \*\*Multitasking \& Multi-user\*\*: Supports running multiple programs and users simultaneously

\- \*\*Lightweight\*\*: Resource-efficient, ideal for older hardware

\- \*\*Simplified Commands\*\*: Streamlined system management



---



\## Essential Linux Commands



\### 1. `sudo su` - Switch to Root User

\*\*Full Form\*\*: Superuser Do Switch User  

\*\*Use\*\*: Switch from normal user to root user with elevated privileges

```bash

sudo su

```



\*\*Identification\*\*:

\- `$` symbol = Normal user (non-administrative privileges)

\- `#` symbol = Root user (superuser privileges)



---



\### 2. `mkdir` - Make Directory

\*\*Full Form\*\*: Make Directory  

\*\*Use\*\*: Create new directories (folders)

```bash

mkdir new\_directory

```



---



\### 3. `ls` - List Files

\*\*Full Form\*\*: List  

\*\*Use\*\*: Lists the contents of a directory

```bash

ls           # List files in current directory

ls -a        # List all files (including hidden files starting with .)

ls -l        # List files in long format with details (directories prefixed with dr)

```



---



\### 4. `cat` - Concatenate

\*\*Full Form\*\*: Concatenate  

\*\*Use\*\*: Display content, combine files, and redirect output

```bash

cat > file.txt           # Create new file and write content (Ctrl+D to save)

cat file.txt             # Display file contents

cat >> file.txt          # Append content to file without overwriting

cat f1 f2 > f3          # Concatenate f1 and f2, write to f3

```



---



\### 5. `stat` - File Status

\*\*Full Form\*\*: Status  

\*\*Use\*\*: Display detailed information about a file or directory (permissions, ownership, size, timestamps)

```bash

stat file.txt

```



---



\### 6. `touch` - Create/Update Files

\*\*Full Form\*\*: Touch  

\*\*Use\*\*: Create empty file or update timestamps

```bash

touch file.txt           # Create empty file

touch .hidden\_file       # Create hidden file (starts with .)

touch -a file.txt        # Update access time

touch -m file.txt        # Update modification time

```



---



\### 7. `clear` - Clear Screen

\*\*Full Form\*\*: Clear Screen  

\*\*Use\*\*: Clears the terminal screen (doesn't delete command history)

```bash

clear

```



---



\### 8. `tac` - Reverse Cat

\*\*Full Form\*\*: Concatenate and Reverse  

\*\*Use\*\*: Display file contents in reverse order (bottom to top)

```bash

tac file.txt

```



---



\### 9. `rev` - Reverse Lines

\*\*Full Form\*\*: Reverse  

\*\*Use\*\*: Reverse characters in each line (mirror image)

```bash

rev file.txt

```



---



\### 10. `rmdir` - Remove Directory

\*\*Full Form\*\*: Remove Directory  

\*\*Use\*\*: Remove empty directories only

```bash

rmdir directory\_name

```



\*\*Note\*\*: Only works on empty directories



---



\### 11. `cd` - Change Directory

\*\*Full Form\*\*: Change Directory  

\*\*Use\*\*: Navigate through directory structure

```bash

cd /path/to/directory    # Navigate to specific directory

cd ..                    # Move up one level (parent directory)

cd                       # Go to home directory

```



---



\### 12. `rm` - Remove Files/Directories

\*\*Full Form\*\*: Remove  

\*\*Use\*\*: Delete files and directories

```bash

rm file.txt              # Remove a file

rm -rf directory\_name    # Recursively remove directory and contents (force)

```



\*\*Warning\*\*: `rm -rf` is powerful and irreversible - use with caution!



---



\### 13. `top` - Task Manager

\*\*Full Form\*\*: Task Manager (Top)  

\*\*Use\*\*: Display real-time system processes and resource usage

```bash

top

```



\*\*Exit\*\*: Press `q` to quit



---



\### 14. `pwd` - Print Working Directory

\*\*Full Form\*\*: Print Working Directory  

\*\*Use\*\*: Display current directory path

```bash

pwd

```



---



\### 15. `vi` - Visual Editor

\*\*Full Form\*\*: Visual Editor  

\*\*Use\*\*: Powerful terminal text editor

```bash

vi file.txt

```



\*\*Modes\*\*:

\- \*\*Normal Mode\*\*: Default mode (navigate, delete, copy, paste)

\- \*\*Insert Mode\*\*: Press `i` to start editing

\- \*\*Command Mode\*\*: Press `Esc` to exit insert mode



\*\*Commands\*\*:

\- `i` - Enter Insert Mode

\- `Esc` - Exit Insert Mode

\- `:wq` - Save and quit

\- `:q!` - Quit without saving



---



\### 16. `nano` - Nano Text Editor

\*\*Full Form\*\*: Nano Text Editor  

\*\*Use\*\*: User-friendly command-line text editor (beginner-friendly)

```bash

nano file.txt

```



\*\*Commands\*\*:

\- Write/edit content directly

\- `Ctrl + X` - Exit editor

\- `Shift + Y` - Confirm save

\- `Enter` - Finalize and return to command line



---



\### 17. `history` - Command History

\*\*Full Form\*\*: History  

\*\*Use\*\*: Display previously executed commands

```bash

history              # Show command history

history -c           # Clear command history

```



---



\## 🚀 Project: EC2 Linux Web Server Deployment using Apache (httpd)



\### Project Overview

Deployed a Linux-based web server on an AWS EC2 instance, configured Apache (httpd), and hosted a custom webpage. Ensured service availability by enabling automatic startup after system reboot.



\### Implementation Steps



\#### 1. 🔐 Gain Administrative Access

```bash

sudo su

```



\#### 2. 📦 Update System Packages

```bash

yum update -y

```



\#### 3. 🌐 Install Apache Web Server

```bash

yum install httpd -y

```



\#### 4. 📁 Create and Deploy Static Webpage

```bash

cd /var/www/html

nano index.html

```



Add your custom HTML content:

```html

<!DOCTYPE html>

<html>

<head>

&nbsp;   <title>My First Web Server</title>

</head>

<body>

&nbsp;   <h1>Welcome to My EC2 Web Server!</h1>

&nbsp;   <p>Successfully deployed using Apache on Amazon Linux</p>

</body>

</html>

```



Save and exit (`Ctrl + X`, `Shift + Y`, `Enter`)



\#### 5. ▶️ Start Apache Service

```bash

systemctl start httpd

systemctl status httpd

```



\#### 6. 🔁 Enable Apache Auto-Start on Reboot

```bash

chkconfig httpd on

\# OR

systemctl enable httpd

```



\#### 7. 🌐 Access Your Web Server

Open browser and navigate to your EC2 instance's public IP:

```

http://your-ec2-public-ip

```



---



\## Technologies Used

\- ☁️ \*\*AWS EC2\*\* - Cloud infrastructure

\- 🐧 \*\*Amazon Linux\*\* - Operating system

\- 🌐 \*\*Apache (httpd)\*\* - Web server

\- 💻 \*\*Linux Command Line\*\* - System administration



---



\## Key Learnings 📚

✅ Linux system administration fundamentals  

✅ Web server deployment on cloud infrastructure  

✅ Service management and persistence configuration  

✅ Hands-on experience with AWS EC2  

✅ Understanding of Linux file system structure  

✅ Package management using YUM  

✅ Security best practices with root access  



---



\## Summary of Essential Commands



| Command | Purpose | Example |

|---------|---------|---------|

| `sudo su` | Switch to root user | `sudo su` |

| `mkdir` | Create directory | `mkdir mydir` |

| `ls` | List files | `ls -la` |

| `cd` | Change directory | `cd /var/www/html` |

| `pwd` | Show current path | `pwd` |

| `cat` | View/create files | `cat file.txt` |

| `nano` | Edit files | `nano index.html` |

| `rm` | Remove files | `rm -rf mydir` |

| `history` | View command history | `history` |



---



\## User Identification Symbols

\- `$` - Normal user (limited privileges)

\- `#` - Root user (administrative privileges)

