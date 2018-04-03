# LinuxConfig

IP Address and SSH Port

#### IP: http://54.209.65.232 SSH:2200

URL to Hosted web app:

#### http://54.209.65.232.xip.io

A summary of software I installed and configuration changes made.

Installed software

        apache2, postgresqlmod-wsgi, pip, sqlalchemy, oauth2client, requests
Configuration Changes
1. Created user grader and gave sudo abilities
2. Generated rsa keys with ssh-keygen and implemented ssh login on grader account 
3. configured ufw to allow only 2200 for ssh 80 for http and 123 for ntp.

##### Creating user grader and give sudo 
1. `sudo adduser grader`
    Create a user named grader
2. `sudo cp /etc/sudoers.d/90-cloud-init-users /etc/sudoers.d/grader`
    Copy sudoers config file to create a new file named grader
3. `sudo vim /etc/sudoers.d/grader`
Use vim to edit the file and give the user grader a sudo capability
##### Generating SSH Keys & Im;lementing ssh login on grader account
1. `sudo ssh-keygen`
    Use ssh-keygen on local machine to generate rsa keys
2. `mkdir .ssh`
    Make a directory in grader account
3. `sudo touch .ssh/authorized_keys`
    Make a directory to hold the keys
4. `sudo nano .ssh/authorized_keys` 
    Edit the authorized_keys file and paste in the public key that was generated
5. `chmod 700 .ssh` & `chmod 644 .ssh/authorized_keys`
    Set permissions so that authorization by ssh will work
##### Configuring the ufw firewall
1. `sudo ufw status`
    Check the status of the firewall
2. `sudo ufw default deny incoming` & `sudo ufw default allow outgoing`
    Configure default settings to block all incoming packets and allow all outgoing
3. `sudo ufw allow 2200`
    Configure the firewall to allow the custom port that is going to be used for ssh
4. `sudo ufw allow 123` & `sudo ufw allow www`
    Configure the firewall to allow http connections and NTP connections

Examples of commands used:
- `sudo ufw deny/allow/status`
- `sudo vim "filename"`
- `sudo adduser grader`
- `sudo ufw allow 2200/www/123`

iv. A list of any third-party resources you made use of to complete this project.

- https://www.linux.com/learn/vim-101-beginners-guide-vim
- https://stackoverflow.com/
- https://support.rackspace.com/how-to/logging-in-with-an-ssh-private-key-on-linuxmac/
- https://www.linux.com/blog/configuring-apache2-run-python-scripts
- http://www.bogotobogo.com/python/Flask/Python_Flask_HelloWorld_App_with_Apache_WSGI_Ubuntu14.php
