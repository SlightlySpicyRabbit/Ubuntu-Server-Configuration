# Ubuntu-Server-Configuration
Used to record the installation and configuration of ubuntu server

## SSH connection
`ssh username@hostname_or_ip_address -p port_number`

## User Account
* **Create User:** Create a new user for better privilege management and file isolation
    * `sudo adduser <username>`

* **Substitute User:** Switching accounts, using sudo permissions can be done without the target account password. If no user is specified, the system attempts to switch to the root account
   * `su - <username>` The environment variable is reinitialized, and the working directory switches to the target user's home directory
   * `su <username>` The environment variables and the working directory are unchanged
   * `sudo -i -u <username>` The environment variable is reinitialized, and the working directory switches to the target user's home directory
   * `sudo -u <username> bash` The environment variables and the working directory are unchanged

* **Change Password:** Forcibly changing the password of the target user can also be used to initialize the password of the root account
   * `sudo passwd <username>` 

## Install Miniconda
* **Download Installation Script:** Download the script from the anaconda website [https://docs.anaconda.com/free/miniconda/](https://docs.anaconda.com/free/miniconda/)
    * `wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh`

* **Run Installation Script:** It is best to run in the target path to avoid selecting a path when conda is installed
    * `bash Miniconda3-latest-Linux-x86_64.sh`

* **Activate Conda:** Select yes during the installation process, conda will automatically change the configuration file, and need to reload the configuration file
    * `source ~/.bashrc`

## Install PostgreSQL
* **Install by APT:** Advanced Package Tool is a package management tool provided with the Ubuntu system
   * `sudo apt update` (Update the package list on Ubuntu system to ensure installing the latest version)
   * `sudo apt install postgresql`

## Setup Git
* **User Name:** The user name will be recorded with each commit and is important for the code hosting repository statistics
   * `git config --global user.name "<username>"`
* **User Email:** The email address will be recorded with each commit and is important for the code hosting repository statistics
   * `git config --global user.email "<example@example.com>"`
