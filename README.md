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

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Prerequisites<h2>
   
- web server:<br />
- iis (internet information Services) installed on Windows.<p>
- nPHP:
- Version 7.3.8 installed. [Download PHP 7.3.8](https://windows.php.net/download/).

- PHP Manager for IIS:
- A tool to manage PHP settings in IIS. [Download PHP Manager for IIS](https://www.iis.net/downloads/microsoft/php-manager).
- URL Rewrite Module:
- Required for URL rewriting. [Download URL Rewrite Module](https://www.iis.net/downloads/microsoft/url-rewrite).

- MySQL:
- Version 5.5.62 installed. [Download MySQL 5.5.62](https://dev.mysql.com/downloads/mysql/5.5.html).

- Database Management Tool:
- heidisql or another MySQL client to manage your database. [Download HeidiSQL](https://www.heidisql.com/download.php).

<h2>Installation Steps:<h2>

<p> 
 
   Create Directory:
   
 <img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Create a folder `C:\PHP` on your server.
-  **Download and Install PHP**:
   - Download PHP 7.3.8 (e.g., `php-7.3.8-nts-Win32-VC15-x86.zip`).
   - Unzip the downloaded file into `C:\PHP`.

### **Install Required Tools:**
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 

 **Install PHP Manager for IIS**:
   - Run the installer `PHPManagerForIIS_V1.5.0.msi` and follow the prompts.
 **Install URL Rewrite Module**:
   - Run the installer `rewrite_amd64_en-US.msi` and follow the prompts.

###  **Set Up MySQL**:

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 
 **Install MySQL**:
   - Run the installer `mysql-5.5.62-win32.msi`.
   - Choose “Typical Setup” during installation.
   - Set the root password to `Password1`.

### 4. **Configure IIS**:

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 Open IIS Manager:

- Launch IIS Manager as an administrator.

 **Register PHP**:
 
 <img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
 
 - Use PHP Manager for IIS to register PHP with IIS.

 **Reload IIS**:

 <img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
 
 - In IIS Manager, restart IIS to apply changes.

###  **Install osTicket**

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

 Download osTicket:
   - Download osTicket version 1.15.8 from the official website or repository.

 **Extract and Move Files**:

  <img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
  - Extract the `upload` folder from the osTicket package.
   - Copy the `upload` folder to `C:\inetpub\wwwroot`.
   - Rename `upload` to `osTicket`.

 **Enable PHP Extensions**:

 <img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
 
 - Open IIS Manager.
   - Navigate to `Sites -> Default -> osTicket`.
   - Double-click “PHP Manager”.
   - Enable the following extensions:
     - `php_imap.dll`
     - `php_intl.dll`
     - `php_opcache.dll`

 **Configure osTicket**:

 <img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
 
 - Rename `ost-sampleconfig.php` to `ost-config.php` in `C:\inetpub\wwwroot\osTicket\include`.
   - Set file permissions:
     - Disable inheritance and remove all existing permissions.
     - Add new permissions for `Everyone` with `Full Control`.

 **Set Up osTicket in the Browser**:

 <img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
 
 - Open a web browser and go to `http://localhost/osTicket`.
   - Click “Continue”.
   - Enter the Helpdesk name and default email address.

### Create and Configure Database

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 **Open HeidiSQL**:
   - Create a new session with username `root` and password `Password1`.
   - Connect and create a new database named `osTicket`.

 **Complete Installation**:

 <img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
 
 - Return to the osTicket setup page in your browser.
   - Enter the MySQL database details:
     - **Database Name**: osTicket
     - **Username**: root
     - **Password**: Password1
     - 
     - <img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
     - Click “Install Now!” to complete the installation.

---
