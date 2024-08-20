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

<h2> Prerequisites <h2>

<p>1. Web Server:
   - **IIS (Internet Information Services)** installed on Windows.<p>
     
2. PHP:
   - Version 7.3.8 installed. [Download PHP 7.3.8](https://windows.php.net/download/).

3. PHP Manager for IIS:
   - A tool to manage PHP settings in IIS. [Download PHP Manager for IIS](https://www.iis.net/downloads/microsoft/php-manager).

4. URL Rewrite Module:
   - Required for URL rewriting. [Download URL Rewrite Module](https://www.iis.net/downloads/microsoft/url-rewrite).

5. MySQL:
   - Version 5.5.62 installed. [Download MySQL 5.5.62](https://dev.mysql.com/downloads/mysql/5.5.html).

6. Database Management Tool:
   - **HeidiSQL** or another MySQL client to manage your database. [Download HeidiSQL](https://www.heidisql.com/download.php).

<h2>Installation Steps/h2>


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

extras to add

Before installing osTicket, ensure you have the following:

1. **Web Server**:
   - **IIS (Internet Information Services)** installed on Windows.

2. **PHP:
   - Version 7.3.8 installed. [Download PHP 7.3.8](https://windows.php.net/download/).

3. **PHP Manager for IIS**:
   - A tool to manage PHP settings in IIS. [Download PHP Manager for IIS](https://www.iis.net/downloads/microsoft/php-manager).

4. **URL Rewrite Module**:
   - Required for URL rewriting. [Download URL Rewrite Module](https://www.iis.net/downloads/microsoft/url-rewrite).

5. **MySQL**:
   - Version 5.5.62 installed. [Download MySQL 5.5.62](https://dev.mysql.com/downloads/mysql/5.5.html).

6. **Database Management Tool**:
   - **HeidiSQL** or another MySQL client to manage your database. [Download HeidiSQL](https://www.heidisql.com/download.php).

## Installation Steps

### 1. **Prepare PHP**

1. **Create Directory**:
   - Create a folder `C:\PHP` on your server.

2. **Download and Install PHP**:
   - Download PHP 7.3.8 (e.g., `php-7.3.8-nts-Win32-VC15-x86.zip`).
   - Unzip the downloaded file into `C:\PHP`.

### 2. **Install Required Tools**

1. **Install PHP Manager for IIS**:
   - Run the installer `PHPManagerForIIS_V1.5.0.msi` and follow the prompts.

2. **Install URL Rewrite Module**:
   - Run the installer `rewrite_amd64_en-US.msi` and follow the prompts.

### 3. **Set Up MySQL**

1. **Install MySQL**:
   - Run the installer `mysql-5.5.62-win32.msi`.
   - Choose “Typical Setup” during installation.
   - Set the root password to `Password1`.

### 4. **Configure IIS**

1. **Open IIS Manager**:
   - Launch IIS Manager as an administrator.

2. **Register PHP**:
   - Use PHP Manager for IIS to register PHP with IIS.

3. **Reload IIS**:
   - In IIS Manager, restart IIS to apply changes.

### 5. **Install osTicket**

1. **Download osTicket**:
   - Download osTicket version 1.15.8 from the official website or repository.

2. **Extract and Move Files**:
   - Extract the `upload` folder from the osTicket package.
   - Copy the `upload` folder to `C:\inetpub\wwwroot`.
   - Rename `upload` to `osTicket`.

3. **Enable PHP Extensions**:
   - Open IIS Manager.
   - Navigate to `Sites -> Default -> osTicket`.
   - Double-click “PHP Manager”.
   - Enable the following extensions:
     - `php_imap.dll`
     - `php_intl.dll`
     - `php_opcache.dll`

4. **Configure osTicket**:
   - Rename `ost-sampleconfig.php` to `ost-config.php` in `C:\inetpub\wwwroot\osTicket\include`.
   - Set file permissions:
     - Disable inheritance and remove all existing permissions.
     - Add new permissions for `Everyone` with `Full Control`.

5. **Set Up osTicket in the Browser**:
   - Open a web browser and go to `http://localhost/osTicket`.
   - Click “Continue”.
   - Enter the Helpdesk name and default email address.

### 6. **Create and Configure Database**

1. **Open HeidiSQL**:
   - Create a new session with username `root` and password `Password1`.
   - Connect and create a new database named `osTicket`.

2. **Complete Installation**:
   - Return to the osTicket setup page in your browser.
   - Enter the MySQL database details:
     - **Database Name**: osTicket
     - **Username**: root
     - **Password**: Password1
   - Click “Install Now!” to complete the installation.

---

This guide provides clear, actionable steps that anyone can follow to install osTicket. It covers all necessary prerequisites and walks through each part of the installation process, ensuring that even users with limited experience can successfully set up osTicket.



