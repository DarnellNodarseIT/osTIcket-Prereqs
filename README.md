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

- Windows 10</b> 

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6


<h2>Installation Steps</h2>


1.) Create a Windows 10 (with 2-4 Virtual CPUs) Virtual Machine through Azure https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Compute%2FVirtualMachines. 
<p>
  - Allow it to create a new Virtual Network. 
<p>
2.) Connect to virtual machine using it's public IP address. 
<p>
- If needed please click on the image to enlarge.
<p>
<img src="https://i.imgur.com/lRnqgWL.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<p>
  - Copy IP address then paste in Remote Desktop Connection.
  - Make sure to click on show options and enter your username which should be "labuser" (if not you will not be able to log in to the virtual machine).
<p>
<img src="https://i.imgur.com/6Z1IUbV.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<p>
  
3.) Once you have connected to your virtual machine you will want to go to your control panel. From the control panel open up programs. Select "Turn Windows features on and off" on the left hand side of the window.

<p>
<img src="https://i.imgur.com/brX0OpO.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<p>
  
4.) Install / Enable IIS in Windows with CGI and Common HTTP Features
  - We're going to want to enable (Internet Information Services)
  - Then we expand (Internet Information Services) and we're gonna enable (Web Management Tools) and (World Wide Web services) and expand (World Wide Web services).
  - Next we're going to enable (Application Development) and expand it.
  - Finally we want to ensure we enable (CGI) and click OK.
    
<img src="https://i.imgur.com/2SF95n0.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>

<p>
<p>

5.) Write 127.0.0.1 in internet explorer and if this shows up then IIS has been setup. 
<p>
<img src="https://i.imgur.com/4ZQbLUL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

6.) Install PHPManager (PHPManagerForIIS_V1.5.0.msi) from Installation Files folder and go through the install wizard.
<p>

<img src="https://i.imgur.com/2eeeS3X.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

7.) Install Rewrite Module (rewrite_amd64_en-US.msi) and go through the install wizard. 
<p>
<img src="https://i.imgur.com/PoicKrW.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
8.) Create the directory C:\PHP:
<p>
- go to (This PC > Windows C: > Create folder "PHP")
<p>
<img src="https://i.imgur.com/YTz5iqV.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<p>

9.) Install PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP.
<p>
<img src="https://i.imgur.com/t5CiAw7.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<p>
<img src="https://i.imgur.com/Ayp8Zy9.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
10.) Install VC_redist.x86.exe. and go through the install wizard.
<p>
11.) Install MySQL 5.5.62 (mysql-5.5.62-win32.msi).
<p>
!! WARNING !! follow these specific instructions carefully.
<p>
- Begin the install Wizard.
<p>
- When asked to choose setup, select (Typical).
<p>
- For server instance configuration, select (Standard Configuration).
<p>
- Finally and most importantly we want to set the user and password to (root) for simplicity purposes. (For precaution open up notepad and type these down as we cannot afford to forget them).
<p>
- Once all of that is done simply Execute and continue on with the guide.
<p>
<img src="https://i.imgur.com/mRXnMsF.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
<img src="https://i.imgur.com/M8XMYwq.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
<img src="https://i.imgur.com/x316K9x.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
<img src="https://i.imgur.com/G2kuX5j.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
12.) Open IIS as an Administrator: 
<p>
<img src="https://i.imgur.com/fcFDYyV.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
<img src="https://i.imgur.com/cZ8WNK3.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
13.) Register PHP from within IIS by first clicking on PHP Manager. 
<p>
- Click on Register new PHP version.
<p>
- Click on the three dots on the right hand side to open file explorer. 
<p>
- Go to (This PC > C: > PHP) and double click (php-cgi.exe) and click ok to register it as the new PHP version.
<p>
- Click on Restart. 
<p>
<img src="https://i.imgur.com/R1POk2E.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
<img src="https://i.imgur.com/fqRXiQH.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
<img src="https://i.imgur.com/z4g3JPZ.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
<img src="https://i.imgur.com/e6WAuMr.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
14.) Install osTicket v1.15.8 
<p>
- First we have to extract the files (You can extract into the folder it's already in which should by This PC > Desktop > osTicket-Installation-Files > osTicket-Installation-Files).
<p>
- Next we're going to open "osTIcket-v1.15.8" and transfer the folder "upload" to folder "wwwroot" (which can be found at This PC > C: > inetpub > wwwroot), we can do this by simply dragging the file over the the other folder.
<p>
- Next we must rename "upload" to "osTicket" !! WARNING !! The spelling for this must be exactly as shown (If it isn't exactly "osTicket" then it will not work).
<p>
- Restart IIS again.
<p>
<img src="https://i.imgur.com/49GtsKt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<p>
<img src="https://i.imgur.com/SJEW1dL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
15.) On IIS go to Sites -> Default Web Site -> osTicket -> On the right, click “Browse *:80”
<p>
<img src="https://i.imgur.com/SoGQjE7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
- Next what you want to see is this site, this means everything you've done up until now has been done correctly.
<img src="https://i.imgur.com/9F0pY9x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
- Next we're going to want to enable some extensions: -> Go back to IIS -> Sites -> Default -> osTicket -> Double click PHP manager -> Click "Enable or disable an extension"
<p>
-Enable: php_imap.dll
<p>
-Enable: php_intl.dll
<p>
-Enable: php_opcache.dll
<p>
<img src="https://i.imgur.com/EyRt2we.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
<img src="https://i.imgur.com/uKXcudd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
<img src="https://i.imgur.com/vbhxjHs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
- Now go back into osTicket and you should have more extensions enabled. 
<p> 
- You will still have "APCu Extension" and "Zend OPcache Extension" disabled, but that's ok.
<p>
<img src="https://i.imgur.com/ZhJHFvi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
16.) Rename ost-sampleconfig.php to ost-config.php.You can find it at (this PC > C: > inetpub > wwwroot > osTicket > include > ost-sampleconfig.php).
<p>
<img src="https://i.imgur.com/qNunqNs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
- Afterwards, right click on ost-config.php and select "Properties"  
  <p>
- From there click Security > Advanced > Disable the inheritance > Remove all inherited permissions from this object.
<p>
- Add new permissions 
<p>
- Select a Principal
<p>
- Write "Everyone" under "Enter the object name to select" (NOTE: This isn't good to do in real life, but for the sake of simplicity we'll keep it like this) then hit OK.
<p>
- Lastly we want to check "Full Control".
<p>
<img src="https://i.imgur.com/rhUVNV3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
17.) Go to osTicket browser page and refresh it. Click Continue on the osTicket browser page. Fill out the page as required except the Database Settings at the bottom of the page. We need to go ahead and install HeidiSQL before continuing as it provides a database and the credentials needed for database settings.
<p>
18.) Install HeidiSQL 
<p>
- Once HeidiSQL finishes installing it will automatically launch. Once opened we want to click new on the bottom left.
<p>
- After clicking new, for user we want to put "root" and for password we want to put "root" like we did for "MySQL server". 
<p>
- Once that's done simply click open.
<p>
<img src="https://i.imgur.com/lDRAzYo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
- Now that we've connected to a session, we want to create a database called "osTicket". !! WARNING !! Once again we want to make sure the database is spelled "osTicket" exactly.
<p>
- Now we want to go back into osTicket a finish filling in the "Database Settings". 
<p>
- MySQL Database: osTicket
<p>
- MySQL Username: root
<p>
- MySQL Password: root 
<p>
- Finally click "Install Now!"
<p>
<img src="https://i.imgur.com/MprFShi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p> 
Congratulations! You've successfully setup osTicket! 
<p>
<img src="https://i.imgur.com/UCD2ICz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
