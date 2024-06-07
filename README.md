# Ubuntu-Server-Configuration
Used to record the installation and configuration of ubuntu server

## SSH connection
`ssh username@hostname_or_ip_address -p port_number`

## User Account
* **Create user:** Create a new user for better privilege management and file isolation
    * `sudo adduser <username>`

* **Substitute User:** Switching accounts, using sudo permissions can be done without the target account password. If no user is specified, the system attempts to switch to the root account
   * `su - <username>` The environment variable is reinitialized, and the working directory switches to the target user's home directory
   * `su <username>` The environment variables and the working directory are unchanged
   * `sudo -i -u <username>` The environment variable is reinitialized, and the working directory switches to the target user's home directory
   * `sudo -u <username> bash` The environment variables and the working directory are unchanged
   * `sudo passwd <username>` Forcibly changing the password of the target user can also be used to initialize the password of the root account

## Install Miniconda
* **Download Installation Script:** Download the script from the anaconda website [https://docs.anaconda.com/free/miniconda/](https://docs.anaconda.com/free/miniconda/)
    * `wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh`

* **Run Installation Script:** It is best to run in the target path to avoid selecting a path when conda is installed
    * `bash Miniconda3-latest-Linux-x86_64.sh`

* **Activate Conda:** Select yes during the installation process, conda will automatically change the configuration file, and need to reload the configuration file
    * `source ~/.bashrc`
 
