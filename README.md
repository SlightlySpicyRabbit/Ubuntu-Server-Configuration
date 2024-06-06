# Ubuntu-Server-Configuration
Used to record the installation and configuration of ubuntu server

## SSH connection
`ssh username@hostname_or_ip_address -p port_number`

## User Account
* **Create user:** Create a new user for better privilege management and file isolation
    * `sudo adduser <username>`
* **Substitute User:**

## Install Miniconda
* **Download Installation Script:** Download the script from the anaconda website
    * `wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh`
* **Run Installation Script:** It is best to run in the target path to avoid selecting a path when conda is installed
    * `bash Miniconda3-latest-Linux-x86_64.sh`
* **Activate Conda:** Select yes during the installation process, conda will automatically change the configuration file, and need to reload the configuration file
    * `source ~/.bashrc`
 
