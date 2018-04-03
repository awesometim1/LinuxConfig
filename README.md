# LinuxConfig

i. The IP address and SSH port so your server can be accessed by the reviewer.

IP: http://54.209.65.232 SSH:2200

ii. The complete URL to your hosted web application.
http://54.209.65.232.xip.io
iii. A summary of software you installed and configuration changes made.
Installed software: apache2, postgresql, mod-wsgi, pip, sqlalchemy, oauth2client, requests, 
Configuration Changes: Created user grader and gave sudo abilities, generated rsa keys with ssh-keygen, implemented ssh login on grader account, configured ufw to allow only 2200 for ssh 80 for http and 123 for ntp.
iv. A list of any third-party resources you made use of to complete this project.
https://www.linux.com/learn/vim-101-beginners-guide-vim
https://stackoverflow.com/
https://support.rackspace.com/how-to/logging-in-with-an-ssh-private-key-on-linuxmac/
https://www.linux.com/blog/configuring-apache2-run-python-scripts
http://www.bogotobogo.com/python/Flask/Python_Flask_HelloWorld_App_with_Apache_WSGI_Ubuntu14.php
