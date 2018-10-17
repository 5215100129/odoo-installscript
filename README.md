# [Odoo](https://www.odoo.com) Install Script
This script is based on the install script from Yenthe Van Ginneken (https://github.com/Yenthe666/InstallScript) but goes a bit further and has been improved. This script will also give you the ability to define an xmlrpc_port in the .conf file that is generated under /etc/. This script can be safely used in a multi-odoo code base server because the default Odoo port is changed before the Odoo is started.

## Installation Procedure

##### 1. Update The OS Packages
```
sudo apt-get update && apt-get -y upgrade
```

##### 2. Download The Script
```
sudo wget https://raw.githubusercontent.com/5215100129/odoo-installscript/master/odoo_install.sh
```
##### 2. Modify The Parameters (optional)
```
sudo nano odoo_install.sh
```
There are a few things you can configure, this is the most used list:<br/>
```OE_USER``` will be the username for the system user.<br/>
```INSTALL_WKHTMLTOPDF``` set to ```false``` if you do not want to install WKHTMLTOPDF.<br/>
```OE_PORT``` is the port where Odoo should run on, for example 8069.<br/>
```OE_VERSION``` is the Odoo version to install, for example ```10.0``` for Odoo 10.0.<br/>
```OE_SUPERADMIN``` is the master password for this Odoo installation.

##### 3. Make The Script Executable
```
sudo chmod +x odoo_install.sh
```
##### 4. Execute The Script
```
sudo ./odoo_install.sh
```
##### 5. Edit The Odoo Configuration
```
sudo nano /etc/odoo-server.conf
```
Set the master admin password:<br/>
```admin_passwd``` will be the password for admin
##### 6. Restart Odoo
```
sudo /etc/init.d/odoo-server restart
```
##### 7. Open Odoo and Create a New Database
```
http://your-server-IP:8069
```