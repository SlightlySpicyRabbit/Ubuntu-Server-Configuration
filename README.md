# Ubuntu-Server-Configuration
Used to record the installation and configuration of ubuntu server

## SSH
* **SSH connection:**
   * `ssh username@hostname_or_ip_address -p port_number`
* **Local Port Forwarding:** Forwards local port to remote port
   * `ssh -L <local port>:localhost:<remote port> <remote user>@remote.example.com`
* **Remote Port Forwarding:** Forwards remote port to local port
   * `ssh -R <remote port>:localhost:<local port> <remote user>@remote.example.com`

## User Account
* **Create User:** Create a new user for better privilege management and file isolation
    * `sudo adduser <username>`

* **Substitute User:** Switching accounts, using sudo permissions can be done without the target account password. If no user is specified, the system attempts to switch to the root account
   * `su - <username>` (environment variable is reinitialized, working directory switches to target user's home directory)
   * `su <username>` (environment variables and the working directory are unchanged)
   * `sudo -i -u <username>` (environment variable is reinitialized, working directory switches to target user's home directory)
   * `sudo -u <username> bash` (environment variables and the working directory are unchanged)

* **Change Password:** Forcibly changing the password of the target user can also be used to initialize the password of the root account
   * `sudo passwd <username>` 

## Install Miniconda
* **Download Installation Script:** Download script from the anaconda website [https://docs.anaconda.com/free/miniconda/](https://docs.anaconda.com/free/miniconda/)
    * `wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh`

* **Run Installation Script:** It is best to run in the target path to avoid selecting a path when conda is installed
    * `bash Miniconda3-latest-Linux-x86_64.sh`

* **Activate Conda:** Select yes during the installation process, conda will automatically change the configuration file, and need to reload the configuration file
    * `source ~/.bashrc`

## Install PostgreSQL
* **Install by APT:** Advanced Package Tool is a package management tool provided with the Ubuntu system
   * `sudo apt update` (update the package list on Ubuntu system to ensure installing the latest version)
   * `sudo apt install postgresql`
 
## PostgreSQL Account
* **Switch To Superuser:** In general, the super administrator does not support remote access and does not allow password login, and can only use sudo to log in to the 'postgres' account in ubuntu
   * `sudo -i -u postgres`
   * `psql` (open the PostgreSQL interactive terminal)
   * `\q` (exit the PostgreSQL interactive terminal)

* **Add User:**
   * `CREATE USER <username> WITH PASSWORD '<password>';`
 
* **Authority Management:**
   * `\du` (lists all PostgreSQL users and their permissions)

## Setup Git
* **User Name:** The user name will be recorded with each commit and is important for the code hosting repository statistics
   * `git config --global user.name "<username>"`
* **User Email:** The email address will be recorded with each commit and is important for the code hosting repository statistics
   * `git config --global user.email "<example@example.com>"`
