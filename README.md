# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Web Server: Apache or Nginx
- Database Server: MySQL or MariaDB
- PHP: Version 7.4 or higher
- PHP Extensions: PDO, mbstring, GD, json, zip, xml, curl
<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>Install / Enable IIS in Windows WITH
CGI and Common HTTP Features and IIS Management Console</p> 
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)<p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>download and install the Rewrite Module (rewrite_amd64_en-US.msi)<p>
</p>Create the directory C:\PHP <p> 
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
</p>download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
If this appears, choose to “Keep” the file <p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>download and install VC_redist.x86.exe<p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)<p>
<br />

extras to add


Prerequisites

Web Server: IIS
PHP: Version 7.3.8
PHP Manager for IIS
URL Rewrite Module
MySQL: Version 5.5.62
Installation Steps

1. Prepare PHP
Create Directory: C:\PHP
Download and Install PHP:
Download PHP 7.3.8 (e.g., php-7.3.8-nts-Win32-VC15-x86.zip).
Unzip it into C:\PHP.
2. Install Required Tools
Install PHP Manager for IIS:
Run PHPManagerForIIS_V1.5.0.msi.
Install URL Rewrite Module:
Run rewrite_amd64_en-US.msi.
3. Set Up MySQL
Install MySQL:
Run mysql-5.5.62-win32.msi.
Choose “Typical Setup”.
Set the root password to Password1 during the configuration process.
4. Configure IIS
Open IIS Manager: Open as an administrator.
Register PHP: Use PHP Manager for IIS to register PHP.
Reload IIS: Stop and start IIS to apply changes.
5. Install osTicket
Download osTicket:
Download version 1.15.8.
Extract and Move Files:
Extract the upload folder from osTicket.
Copy the upload folder to C:\inetpub\wwwroot.
Rename upload to osTicket.
Enable PHP Extensions:
Open IIS Manager.
Navigate to Sites -> Default -> osTicket.
Double-click “PHP Manager”.
Enable the following extensions:
php_imap.dll
php_intl.dll
php_opcache.dll
Configure osTicket:
Rename ost-sampleconfig.php to ost-config.php in C:\inetpub\wwwroot\osTicket\include.
Set file permissions:
Disable inheritance and remove all existing permissions.
Add new permissions for Everyone with Full Control.
Set Up osTicket in the Browser:
Open your browser and go to http://localhost/osTicket.
Click “Continue”.
Enter the Helpdesk name and default email address.
6. Create and Configure Database
Open MySQL Workbench or HeidiSQL:
Connect using username root and password Password1.
Create a new database named osTicket.
Complete Installation:
Return to the osTicket setup page.
Enter the MySQL database details:
Database Name: osTicket
Username: root
Password: Password1
Click “Install Now!”




