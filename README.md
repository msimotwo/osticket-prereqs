<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
Hello, my name is Meshach Simotwo and I am a IT Professional. Today I will be showing you the steps to installing and configuring osTicket. This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

*<h2>Environments and Technologies Used</h2>*

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

*<h2>Operating Systems Used </h2>*

- Windows 10 Pro</b> 
- Size: Preferably 2 or 4 vcpu's, 16GiB memory</b>

*<h2>List of Prerequisites</h2>*

<p>
<img src="https://i.imgur.com/3eApv1B.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

- Making Resource Group's and Virtual Machines in Microsoft Azure!
  - Create a Resource Group and name it "osTicketRG"
  - Create an Azure Virtual Machine Windows 10, 4 vCPUs
  - Name: "Vm-osticket"
  - Username: "labuser" (for example/whatever you chose)
  - Password: "osTicketPassword1!" (for example/whatever you chose)

*<h2>Links for Installation</h2>*

https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
- We will use these files to install osTicket and some of the dependencies. I’m using this offline version to make sure everyone is using the same version of all the files :)

*<h2>Instructions for installation</h2>*

<p>
<img src="https://i.imgur.com/LuPky7l.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

- Install / Enable IIS in Windows WITH CGI
  - World Wide Web Services -> Application Development Features -> [X] CGI
  - From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

  - From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)

Create the directory C:\PHP
- From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP

- From the Installation Files, download and install VC_redist.x86.exe.

- From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  - Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration -> Password1
- Open IIS as an Administrator. (Right click on IIS and click "Run as Administrator")
  - Register PHP from the IIS
  - Reload IIS (Open IIS, Stop and Start the server)
  - Install osTicket v1.15.8
    - Download osTicket from the Installation Files Folder
    - Extract and copy “upload” folder to c:\inetpub\wwwroot
    - Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”
- Reload IIS (Open IIS, Stop and Start the server)
- Go to sites -> Default -> osTicket
    - On the right, click “Browse *:80”
- Note that some extensions are not enabled
  - Go back to IIS, sites -> Default -> osTicket
  - Double-click PHP Manager
  - Click “Enable or disable an extension”
    - Enable: php_imap.dll
    - Enable: php_intl.dll
    - Enable: php_opcache.dll
    - Refresh the osTicket site in your browse, observe the changes
 - Rename: ost-config.php
    - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
    - To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
      - *When renaming a file, remember to right click on the file name, then press "Rename". Once you have entered your desired name, press the Enter button and it will rename itself.*
 - Assign Permissions: ost-config.php
    - Disable inheritance -> Remove All
    - New Permissions -> Everyone -> All
 - Continue Setting up osTicket in the browser (click Continue)
    - Name Helpdesk
    - Default email (receives email from customers)
 - From the Installation Files, download and install HeidiSQL.
    - Open Heidi SQL

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

    - Create a new session 
        - Login Credentials: root/Password1
    - Connect to the session
    - Create a database called “osTicket”
 - Continue Setting up osticket in the browser
    - MySQL Database: osTicket
      - MySQL Username: root
      - MySQL Password: Password1
    - Click “Install Now!”
- Congratulations, hopefully it is installed with no errors!
    - Browse to your help desk login page: http://localhost/osTicket/scp/login.php
    - End Users osTicket URL:
    http://localhost/osTicket/
- Clean up
    - Delete: C:\inetpub\wwwroot\osTicket\setup
      - Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
- Side Notes
    - Browse to your help desk login page: 
    http://localhost/osTicket/scp/login.php  
    - End Users osTicket URL:
    http://localhost/osTicket/ 
    
*<h2>Post-Installation Instructions</h2>*
   - Configure Roles
      - Admin Panel -> Agents -> Roles
      - Supreme Admin
   - Configure Departments
      - Admin Panel -> Agents -> Departments
      - System Administrators
   - Configure Teams
      - Admin Panel -> Agents -> Teams
          - Level I Support
          - Level II Support
      - Allow anyone to create tickets
          - Admin Panel -> Settings -> User Settings
          - Registration Required: Require registration and login to create tickets
   - Configure Agents (workers)
      - Admin Panel -> Agents -> Add New
          - Jane
          - John
   - Configure Users (customers)
       - Agent Panel -> Users -> Add New
          - Karen
          - Ken
   - Configure SLA
       - Admin Panel -> Manage -> SLA
          - *Sev-A* (1 hour, 24/7)
          - *Sev-B* (4 hours, 24/7)
          - *Sev-C* (8 hours, business hours)
   - Configure Help Topics
       - Admin Panel -> Manage -> Help Topics
          - Business Critical Outage
          - Personal Computer Issues
          - Equipment Request
          - Password Reset
          
*<h2>Tickets and Ticket Lifecycle</h2>*

   - Just practice creating, changing, and solving tickets. I recommend doing this lab over and over to help build skills and memory of osTicket creation.
   - Ticket examples:
        - *Sev-A* (1 hour, 24/7) [entire mobile/online banking system is down] -> SysAdmins
        - *Sev-B* (4 hours, 24/7) [accounting department needs adobe upgrade, broken]
        - *Sev-B/C* (2 hours, business hours) [CFO’s laptop seems a bit slow]


       













      




















