<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
Hello, my name is Meshach Simotwo and I am a IT Professional. Today I will be showing you the steps to installing and configuring osTicket. This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 Pro</b> 
- Size: Preferably 2 or 4 vcpu's, 16GiB memory</b>

<h2>List of Prerequisites</h2>

- Making Resource Group's and Virtual Machines in Microsoft Azure!
  - Create a Resource Group and name it "osTicketRG"
  - Create an Azure Virtual Machine Windows 10, 4 vCPUs
  - Name: "Vm-osticket"
  - Username: "labuser" (for example/whatever you chose)
  - Password: "osTicketPassword1!" (for example/whatever you chose)

<h2>Links for Installation</h2>

https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
- We will use these files to install osTicket and some of the dependencies. I’m using this offline version to make sure everyone is using the same version of all the files :)

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



- Item 5

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Blah Blah Blah.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
