# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- microsoft azure (virtual machines/compute)
- remote desktop
- internet information services (iis)

# osTicket Installation Guide

## Overview
osTicket is an open-source support ticket system that helps organizations manage customer inquiries efficiently. This guide provides detailed prerequisites and step-by-step installation instructions.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Installation Steps](#installation-steps)
- [Configuration](#configuration)
- [Key Features](#key-features)
- [Troubleshooting](#troubleshooting)
- [Additional Resources](#additional-resources)


## Prerequisites
Before installing osTicket, ensure your server meets the following requirements:

### System Requirements
- **Operating System**: Ubuntu 20.04 or later (similar steps apply for other Linux distributions)
- **Web Server**: Apache or Nginx
- **PHP**: Version 7.2 or higher
  - Required PHP extensions:
    - `php-mysql`
    - `php-xml`
    - `php-mbstring`
    - `php-zip`
- **Database**: MySQL version 5.5 or higher

### Installing Prerequisites
Run the following commands to install the necessary packages on an Ubuntu server:

```bash
sudo apt update
sudo apt install apache2 php libapache2-mod-php php-mysql php-xml php-mbstring php-zip mysql-server wget unzip
```

## Installation Steps

### Step 1: Download osTicket
1. Navigate to the web server's root directory:
   ```bash
   cd /var/www/html
   ```
2. Download the latest version of osTicket:
   ```bash
   wget https://github.com/osTicket/osTicket/releases/download/v1.15.4/osTicket-v1.15.4.zip
   ```
3. Unzip the downloaded file and rename the directory:
   ```bash
   unzip osTicket-v1.15.4.zip
   mv upload osTicket
   ```

### Step 2: Set Directory Permissions
Set the appropriate permissions for the osTicket directory:
```bash
sudo chown -R www-data:www-data /var/www/html/osTicket
sudo chmod -R 755 /var/www/html/osTicket
```

### Step 3: Create a Database
1. Log into the MySQL server:
   ```bash
   mysql -u root -p
   ```
2. Create a database and user for osTicket:
   ```sql
   CREATE DATABASE osticket;
   CREATE USER 'osticketuser'@'localhost' IDENTIFIED BY 'your_password';
   GRANT ALL PRIVILEGES ON osticket.* TO 'osticketuser'@'localhost';
   FLUSH PRIVILEGES;
   EXIT;
   ```

### Step 4: Configure Apache
Create a new configuration file for osTicket:
```bash
sudo nano /etc/apache2/sites-available/osticket.conf
```
Add the following configuration (adjust `ServerName` as necessary):
```apache
<VirtualHost *:80>
    ServerName your-domain.com
    DocumentRoot /var/www/html/osTicket

    <Directory /var/www/html/osTicket>
        AllowOverride All
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/osticket_error.log
    CustomLog ${APACHE_LOG_DIR}/osticket_access.log combined
</VirtualHost>
```
Enable the new site and rewrite module:
```bash
sudo a2ensite osticket
sudo a2enmod rewrite
sudo systemctl restart apache2
```

### Step 5: Complete the Web Installation
1. Open your web browser and navigate to `http://your-domain.com`.
2. Follow the on-screen instructions to complete the osTicket setup:
   - Input database details (database name, user, password).
   - Set up your admin account.
3. Once installation is complete, delete the setup directory for security:
   ```bash
   sudo rm -rf /var/www/html/osTicket/setup/
   ```

## Configuration
After installation, configure osTicket through the admin panel. Important settings include:
- Email settings for ticket notifications.
- Department setup for managing inquiries.
- Customization of fields and forms as needed.

## Key Features
- **Ticket Management**: Easily track and manage customer inquiries.
- **Email Integration**: Automatically convert emails to tickets.
- **Customizable Help Topics**: Tailor support requests to your needs.
- **User Portal**: A user-friendly interface for customers to submit and track tickets.

## Troubleshooting
- **Common Issues**: If you encounter issues, check the permissions and ensure all prerequisites are installed.
- **Database Connection Errors**: Double-check the database credentials and MySQL service status.
- **Logs**: Check Apache logs for errors:
  ```bash
  tail -f /var/log/apache2/osticket_error.log
  ```

## Additional Resources
- [osTicket Documentation](https://osticket.com/docs/)
- [osTicket GitHub Repository](https://github.com/osTicket/osTicket)



