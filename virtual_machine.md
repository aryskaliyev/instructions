1. Install OS Ubuntu on virtual machine
2. SSH key:
```
cat ~/.ssh/id_rsa.pub
```
3. Connect to virtual machine with SSH:
```
 ssh www@<public ip>
```
4. Update & install
```
sudo apt-get update
sudo apt-get install -y vim mosh tmux htop git curl wget unzip zip gcc build-essential make
```
- **MOSH** (mobile shell) -- is a tool used to connect from a client computer to a server over the Internet, to run a remote terminal.
- **TMUX** -- is an open-source terminal multiplexer for Unix-like operating systems. It allows multiple terminal sessions to be accessed simultaneously in a single window. It is useful for running more than one command-line program at the same time. It can also be used to detach processes from their controlling terminals, allowing remote sessions to remain active without being visible.
- **HTOP** -- is an interactive system-monitor process-viewer and process-manager. It is designed as an alternative to the Unix program top.
- **CURL** -- is a computer software project providing a library (libcurl) and command-line tool (curl) for transferring data using various network protocols. The name stands for "Client for URL".
- **WGET** -- is a computer program that retrieves content from web servers. It is part of the GNU Project. Its name derives from "World Wide Web" and "get". It supports downloading via HTTP, HTTPS, and FTP.
- **GCC** -- The GNU Compiler Collection (GCC) is an optimizing compiler produced by the GNU Project supporting various programming languages, hardware architectures and operating systems. 
- **BUILD-ESSENTIAL** -- The build-essentials packages are the form of meta-packages that are essential to compile software. They contain the GNU/g++ compiler collection, GNU debugger, and a few more libraries and tools that are needed for compiling a program. A few other packages, like GCC, make, G++, dpkg-dev, etc., are also installed on our system when we install the build-essential packages.
- **MAKE** -- is a build automation tool that builds executable programs and libraries from source code by reading files called Makefiles which specify how to derive the target program. Though integrated development environments and language-specific compiler features can also be used to manage a build process, Make remains widely used, especially in Unix and Unix-like operating systems.

5. On remote machine, enable www login, disable root login, disable SSH login by password -- just keys
```
sudo vim /etc/ssh/sshd_config
  AllowUsers www root
  PermitRootLogin no
  PasswordAuthentication no
  
sudo service ssh restart
sudo passwd www
```
