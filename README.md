
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

- Azure Virture Machine
- osTicket Installation files
- Heidi SQL

<h2>Installation Steps</h2>

<p>
</p>
<p>
For installation, we need to create a virtual machine using the Microsoft Azure portal. Inside the portal, we will be using a VM which is a remote computer(separate from your main computer). We are using a VM in order to protect our physical machine in case something breaks. In Azure, create a resource group and title it "osTicket". Next, create a VM with 2 or 4 CPUs. For this setup, 4 CPUs is preferred.

 <img src="https://i.imgur.com/8lEQRrQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
</p>  
<br />
<p>
</p>
Next, connect your newly created VM using Remote Desktop and using the public IPv4 address.
</p>
<img src="https://i.imgur.com/rGzZZp4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
</p>
<p>
Now that you are connected, you will enable IIS. In your remote desktop, click the control panel then select uninstall a program. Off to the left, select "Turn windows features on or off". A list will appear then you will enable Internet Information Services.
<p> 
<img src="https://i.imgur.com/qKgwDMD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
</p>
<p>
Since we have enabled IIS, we need to install Web Platform Installer. Here is the link:                                                                             https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
 This link will provide you with all the material you need to download to get osTicket up and running. Simply click the link and install 
</p>
<img src="https://i.imgur.com/8hDn4qj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p> 
Once you have installed Web Installer Platform, will download and install the following: PHP Manager for IIS, Rewrite Module, PHP 7.3.8(unzip contents into C:\PHP), VC redist.x86.exe, and last MySQL 5.5.62.
</p>
<img src="https://i.imgur.com/hoZn1kG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
</p>
<p>
To download osTicket, download osTicket from installation file folder, extract and copy "upload" folder to c:\inetpub\wwwroot. Within c:\inetpub\wwwroot, rename "upload" to "osTicket". In IIS, click restart then go to sites-default-osTicket, and click "Browse:80" and the osTicket Installer should appear.
</p>
<img src="https://imgur.com/5FXtOzK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br /> 
<p> 
</p> 
<p> 
 To enable osTicket, go to IIS-sites-default-osTicket, click on PhP manager, click enable an extention and enable the following: php_imap.dll,php_intl.dll, and opcache.dll. Refresh the os Ticket site in your browser, observe the changes.
</p> 
 <img src="https://imgur.com/xMGdu7w.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<p> 
</p> 
<p> 
To rename ost-config.php in the osticket file, go to files, go to c:drive, click on osticket-click on include-click on ost-smpleconfig.php and rename it ost-config.php.
To assign permisssion, right click ost-config.php, click on properties-security-advance-disable inheritance. Remove all permissions and then add permission-select principal-type "everyone"-check names-full control.
</p> 
 <img src="https://imgur.com/Wl3swdt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<p> 
</p> 
<p> 
Continue setting up osTicket in the browser
Name help desk
Select a default email that will receive emails from customers who submit tickets.
</p> 
 <img src="https://imgur.com/Y3Z4wLb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<p> 
</p> 
<p> 
Continue setting up osticket in the browser MySQL(username-root) (password-Password1). Click install now
</p> 
 <img src="https://imgur.com/pm99h5q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<p>
<p>
If there are no errors, it should read "Congratulations"
Clean up
Delete: C:\inetpub\wwwroot\osTicket\setup
Set permissions to "read" only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
Login to the osTicket Admin Panel(http://localhost/osTicket/scp/login.php)
