# osticket-prereqs

<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>
 
- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create a Resource Group in Azure ( Name it: RG-osTicket )
- Create an Azure Virtual Machine Windows 10, 4 vCPUs
    - Name: Vm-osticket
    - Username: (Whatever You Chose)
    - Password: (osTicketPassword1!) or (Whatever You Chose)
- Open osTicket [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
    - We will use these files to install osTicket and some of the dependencies  

<h2>Installation Steps</h2>

- Install / Enable IIS in Windows WITH CGI and Common HTTP Features
     - World Wide Web Services ->
     - Application Development Features ->
       
       [X] CGI
       
       [X] Common HTTP Features
       
-  From [Installation files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) download and install [PHP Manager for IIS](https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view?usp=share_link)
  - From [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) download and install the [Rewrite Module](https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view?usp=share_link)
- Create the directory C:\PHP
-  From [Installation files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) download [PHP 7.3.8](https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=share_link) and unzip the contents into C:\PHP
-  From [Installation files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) download and install [VC_redist.x86.exe.](https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view?usp=share_link)
-  From [Installation files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) download and install [MySQL 5.5.62](https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view?usp=share_link)

    - Typical Setup ->
    - Launch Configuration Wizard (after install) ->
    - Standard Configuration ->
    -Password1
- Open IIS as an Admin
- Register PHP from within IIS
- Reload IIS (Open IIS, Stop and Start the server)
- Install osTicket v1.15.8
  - Download osTicket from the Installation Files Folder
  - Extract and copy “upload” folder to c:\inetpub\wwwroot
  - Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”
- Reload IIS (Open IIS, Stop and Start the server)
-  Go to sites -> Default -> osTicket
    - On the right, click “Browse *:80”
- Note that some extensions are not enabled
    - Go back to IIS, sites -> Default -> osTicket
    - Double-click PHP Manager
    - Click “Enable or Disable an Extension”
         - Enable: php_imap.dll
         - Enable: php_intl.dll
         - Enable: php_opcache.dll
    - Refresh the osTicket site in your browse, observe the changes
- Rename: ost-config.php
     - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
     - To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
- Assign Permissions: ost-config.php
     - Disable inheritance -> Remove All
     - New Permissions -> Everyone -> All
- Continue Setting up osTicket in the browser (click Continue)
     - Name Helpdesk
     - Default email (receives email from customers)  
- From the  [Installation files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) download and install [HeidiSQL](https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit)
     - Open Heidi SQL
     - Create a new session, root/Password1
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
     - http://localhost/osTicket
      
 - Clean up
     - Delete: C:\inetpub\wwwroot\osTicket\setup
     - Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php

 - Notes:
     - Browse to your help desk login page: http://localhost/osTicket/scp/login.php
     - End Users osTicket URL: http://localhost/osTicket/ 









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

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
