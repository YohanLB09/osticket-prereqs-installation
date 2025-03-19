# <p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" height="100%" width="100%" alt="Setting Up in Azure"/>
<br />

<h1>osTicket: Prerequisites and Installation</h1>

<h2>Description</h2>
In this guided lab, we will setup an osTicket system from scratch via a Windows 10 Virtual Machine created in Azure.<br/>
<br/>

<h2>Environments and Technologies</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- Internet Information Services (IIS)


<h2>Operating Systems Used </h2>

- Windows 10 Pro, version 22H2


<h2>High-Level Steps</h2>

- Step 1: Create a Resource Group and a Virtual Machine
- Step 2: Connect to the Windows Virtual Machine
- Step 3: Download and Extract the osTicket installation folder
- Step 4: Install and Enable IIS with CGI
- Step 5: Install the PHP Manager
- Step 6: Install the Rewrite Module
- Step 7: Create a directory for PHP files
- Step 8: Extract PHP files
- Step 9: Install a Microsoft Visual C++ Redistributable
- Step 10: Install MySQL
- Step 11: Configure MySQL
- Step 12: Register PHP in IIS
- Step 13: Reload IIS
- Step 14: Install osTicket
- Step 15: Load the osTicket Web Site
- Step 16: Enable osTicket extensions
- Step 17: Rename a specific configuration file
- Step 18: Assign permissions to the configuration file
- Step 19: Install a HeidiSQL database
- Step 20: Configure the HeidiSQL database
- Step 21: Configure basic osTicket settings
- Step 22: Login to osTicket 
- Step 23: Lab cleanup 


<h2>Installation Steps</h2>

<h3>Step 1: Create a Resource Group and a Virtual Machine</h3>
<p>
<img src="https://i.imgur.com/gNaBAwe.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-You need to create a Resource Group prior to configuring a Virtual Machine. Check out this guided lab if needed: https://github.com/YohanLB09/azure-vm-network-analysis-part1-prereqs. 

-If you know how to create both, just remember to use the "Windows 10 Pro version 22H2" image, and at least 2 vCPUs and 8 GiB of memory.

-Also, make sure you remember the credentials to connect to the Windows VM (use Notepad).
</p>
<br />




<h3>Step 2: Connect to the Windows Virtual Machine</h3>
<p>
<img src="https://i.imgur.com/j05uyJg.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Go to Remote Desktop Connection.

-Connect to the Windows VM with its public IP address, and then insert the credentials to log into the VM.
</p>
<br />




<h3>Step 3: Download and Extract the osTicket installation folder</h3>
<p>
<img src="https://i.imgur.com/0ZPAuJv.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-In your Windows VM, open Microsoft Edge.

-Download the osTicket installation folder from this Google Drive link: 
https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD.

-Open File Explorer, navigate to "Downloads" and locate the "osTicket-Installation-Files" compressed folder.

-Right-click on the folder and select "Extract All". Ensure the extraction destination is set to "Desktop" and the folder is named "osTicket-Installation-Files". We will use the files in this folder to install osTicket and some of its dependencies.

-Click "Extract".

Now, the installation files are uncompressed and ready to be used normally (open, edit, move).
</p>
<br />




<h3>Step 4: Install and Enable IIS with CGI</h3>
<p>
<img src="https://i.imgur.com/IdQf6vA.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Navigate to the Control Panel, then click on "Programs" -> "Programs and Feature" -> "Turn Windows features on or off" ->  check the box for "Internet Information Services" and click on the [X] to expand -> expand "World Wide Web Services" -> expand "Application Development Features" -> check the box for "CGI" and click on "OK" to validate the changes.

This setup enables IIS to run dynamic web applications like osTicket, allowing it to process PHP scripts (required by osTicket) and serve the web pages properly. 
</p>
<br />


<p>
<img src="https://i.imgur.com/3Xpn647.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-You can also ensure that the web server (IIS) has been installed correctly by testing the loopback IP address (127.0.0.1) in Microsoft Edge. You should see a default page appearing.
</p>
<br />




<h3>Step 5: Install the PHP Manager</h3>
<p>
<img src="https://i.imgur.com/oJR0C5s.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Go back to the Desktop and open the "osTicket-Installation-Files" folder.

-Click on "PHPManagerforIIS_V1.5.0" and complete the installation process.

This ensures that IIS can correctly run PHP scripts, which is necessary for osTicket to function properly on your Windows 10 VM. 
</p>
<br />




<h3>Step 6: Install the Rewrite Module</h3>
<p>
<img src="https://i.imgur.com/Fi40B8n.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-From within the "osTicket-Installation-Files" folder, click on "rewrite_amd64_en-US" and complete the installation process.

This enables URL management and ensures osTicket's URLs are clean and functional.
</p>
<br />




<h3>Step 7: Create a directory for PHP files</h3>
<p>
<img src="https://i.imgur.com/7DCdsaD.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Without closing the "osTicket-Installation-Files" folder window, open a new File Explorer window.

-From there, navigate to the C: drive and create a new folder called "PHP".
</p>
<br />




<h3>Step 8: Extract PHP files</h3>
<p>
<img src="https://i.imgur.com/crABod2.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Back to the window where the "osTicket-Installation-Files" folder is open, right click on "php-7.3.8-nts-Win32-VC15-x86" and select "Extract All".

-When asked to select a destination folder to extract PHP files, browse to Windows (C:) -> "PHP" folder -> "Select Folder" -> "Extract".

This process uncompresses the PHP files so they can be used for IIS and osTicket configuration, and it organizes them in C:\PHP to make them easily accessible for setup and execution.
</p>
<br />




<h3>Step 9: Install a Microsoft Visual C++ Redistributable</h3>
<p>
<img src="https://i.imgur.com/bQH7sa7.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-From within the "osTicket-Installation-Files" folder, click on "VC_redistx86" and complete the installation process.

This step installs the necessary Visual C++ libraries that osTicket needs to run properly, preventing errors related to missing or unavailable essential code (DLL files).
</p>
<br />




<h3>Step 10: Install MySQL</h3>
<p>
<img src="https://i.imgur.com/RZvewKC.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Back in the "osTicket-Installation-Files" folder, click on "mysql-5.5.62-win32" and initiate the installation process.

-When asked to choose the setup type during the installation process, select "Typical". 

-Complete the installation process.

This step installs MySQL, a database software required by osTicket to store and manage data like tickets and user information.
</p>
<br />




<h3>Step 11: Configure MySQL</h3>
<p>
<img src="https://i.imgur.com/7gjXXIt.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-After the installation process is completed, launch the configuration wizard and choose "Standard Configuration" for the configuration type. 

-Leave the Windows options as default and click "Next".

-When prompt to enter credentials, create a simple password (ex: root) and make sure you remember it. 
(This is not best practice in terms of security, but for the purpose of this guided lab, we want to keep it as simple as possible to prevent issues during the installation process).

-Complete the configuration process. 

This step sets up MySQL with default settings and a simple password, ensuring osTicket can connect to and use the database.
</p>
<br />




<h3>Step 12: Register PHP in IIS</h3>
<p>
<img src="https://i.imgur.com/yuZXLua.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-From the Windows Desktop search bar, type IIS and open IIS Manager as an Admin.

-In IIS Manager, click on "PHP Manager"-> "Register new PHP version" ->  click on "..." to browse in File Explore ->  "Windows (C:)" -> "PHP" folder ->  "php-cpi" ->  "OK"

This step connects PHP (the language osTicket runs on) to IIS (the web server) so that IIS can process and run PHP code correctly for osTicket.
</p>
<br />




<h3>Step 13: Reload IIS</h3>
<p>
<img src="https://i.imgur.com/lxx2rpK.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Back in IIS manager, under "Connections", right-click on "osTicket-VM", and then click on "Stop". 

-Wait for it to stop, and then click on "Start".

This step restarts IIS to ensure that any changes made during the installation are properly applied to osTicket.
</p>
<br />




<h3>Step 14: Install osTicket</h3>
<p>
<img src="https://i.imgur.com/pYsAz3b.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Back to the "osTicket-Installation-Files" folder, extract the “osTicket-v1.15.8” folder in the same location as it is. 
This will open a new window showcasing uncompressed internal folders; "scripts" and "upload".
</p>
<br />


<p>
<img src="https://i.imgur.com/bvAAO1L.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Next, from the new window, copy the “upload” folder into “C:\inetpub\wwwroot”

-Within “C:\inetpub\wwwroot”, Rename “upload” to “osTicket” (make sure you don't make any mistakes here).

-Just like in step 13, Open ISS as the admin, Stop and Start the server again.

This step prepares osTicket for use by extracting its files and placing them in the IIS web server directory (C:\inetpub\wwwroot). Renaming the folder to "osTicket" ensures the system recognizes it as the main application directory. 
Restarting IIS again applies any final changes, ensuring osTicket runs smoothly after installation.
</p>
<br />




<h3>Step 15: Load the osTicket Web Site</h3>
<p>
<img src="https://i.imgur.com/TA61pqT.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-In ISS Manager, under "Connections", expand "osticket-vm (...)" -> expand "Sites" -> expand "Default Web Site" -> click on "osTicket" -> on the right, click on “Browse *:80”
</p>
<br />


<p>
<img src="https://i.imgur.com/26woY7s.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-You should be redirected to the osTicket installer web page.
(If you don't see the website appearing as intended, you may have done something wrong along the way. In this case, I recommend reviewing previous steps to ensure that you didn't forget anything).

This step allows you to launch the osTicket web installer in your browser by using IIS Manager. Clicking *“Browse :80” opens the osTicket setup page, where you can configure the helpdesk system.
</p>
<br />




<h3>Step 16: Enable osTicket extensions</h3>
<p>
<img src="https://i.imgur.com/p9qhSgL.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
If the osTicket web site loaded as intended, you will notice that some extension are not enabled. This is normal since we haven't enabled all the osTicket extensions yet.

-To remediate to this, go back to IIS, under "Connections", expand "osticket-vm (...)" -> expand "Sites" -> expand "Default Web Site" -> click on "osTicket" -> "PHP Manager" -> "Enable or disable an extension".

-From the PHP Extensions window, right click and then enable the following PHP extensions: "php_imap.dll", "php_intl.dll", "php_opcache.dll".
</p>
<br />


<p>
<img src="https://i.imgur.com/8qJMHZZ.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Go back to the osTicket web site and refresh it. You should notice that some of the extensions that were disabled previously are now active. The remaining extensions are not required for the installation of osTicket.

This step enables specific PHP extensions needed for osTicket to function properly. These extensions support email fetching, localization, and performance optimization. 
</p>
<br />




<h3>Step 17: Rename a specific configuration file</h3>
<p>
<img src="https://i.imgur.com/AVFPxFu.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Go to File explorer and navigate to Windows (C:) -> inetpub -> wwwroot-> osTicket -> include

-From here rename the "ost-sampleconfig.php" file to "ost-config.php".

This step renames a required configuration file so osTicket can recognize and use it for storing important settings, like database connection details.
</p>
<br />




<h3>Step 18: Assign permissions to the configuration file</h3>
<p>
<img src="https://i.imgur.com/QIM4N3b.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Right click on the "ost-config.php" file and go to "Properties" -> "Security" -> "Advanced" -> "Disable inheritance" -> "Remove all inherited permissions from this object" -> "Add" -> "Select a principal" -> under "Enter the object name to select", type "everyone" ->  "Check Names" -> "OK" -> under basic permissions, check the "Full control" box -> "OK" -> "Apply" -> "OK"

This step ensures osTicket can properly access and modify the ost-config.php file by granting full control to all users, preventing permission-related errors.
</p>
<br />




<h3Step 19: Install a HeidiSQL database</h3>
<p>
<img src="https://i.imgur.com/TWe4jx5.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Go back to the “osTicket-Installation-Files” folder, click on "HeidiSQL_12.3.0.6589_Setup" and complete the installation process (leave all options as default).
</p>
<br />




<h3>Step 20: Configure the HeidiSQL database</h3>
<p>
<img src="https://i.imgur.com/uYRmpfn.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Once the installation process is completed and HeidiSQL is launched, click on "New" -> under "Settings", type "root" for the "Password" -> "Open"
</p>
<br />


<p>
<img src="https://i.imgur.com/BTZoxk3.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-On the new window, right click on "Unnamed" -> expand "Create New" -> "Database" -> type "osTicket" for the "Name" -> "OK".

This step installs HeidiSQL, a tool for managing MySQL databases, and creates the osTicket database, where all ticket-related information will be stored.
</p>
<br />




<h3>Step 21: Configure basic osTicket settings</h3>
<p>
<img src="https://i.imgur.com/GQ5pz1D.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Back on the osTicket website, click on "Continue".

-On the "osTicket Basic Installation" page, Under "System Settings", setup "Helpdesk Name", and "Default Email".

-Under "Admin User",  setup "First Name", "Last Name", "Email Address" (use a different one than for System Settings), "Usersame" and "Password" (create new credentials specifically for the admin user).

-Under "Database Settings", insert "osTicket" for "MySQLDarabase", type "root" for "MySQL Username" and "MySQL Password", and click on "Install Now".
</p>
<br />


<p>
<img src="https://i.imgur.com/Yxaf3JC.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-You should be redirected to the osTicket installation Congratulation page. This also includes the URLs for different access to the osTicket environment(end-user, admin, etc).

-Note the URLs in Notepad.

This step sets up basic information for osTicket. It also connects osTicket to the MySQL database to store data and finalizes the installation.
</p>
<br />




<h3>Step 22: Login to osTicket</h3>
<p>
<img src="https://i.imgur.com/RWCXeOl.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Open a new tab in Microsoft Edge and browse to your help desk login page: http://localhost/osTicket/scp/login.php.

-Login with your admin credentials. 
</p>
<br />


<p>
<img src="https://i.imgur.com/xC948zO.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-If you logged in to your help desk portal successfully, you should notice a single ticket, this simply indicates that osTicket has been installed.
</p>
<br />


<p>
<img src="https://i.imgur.com/8ujnQP7.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Open a new tab and browse to the end user portal to ensure that it can be accessed too: http://localhost/osTicket/.
</p>
<br />




<h3>Step 23: Lab cleanup</h3>
<p>
<img src="https://i.imgur.com/ruluAYE.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Back in File Explorer, navigate to C:\inetpub\wwwroot\osTicket

-Delete the "setup" folder.
</p>
<br />


<p>
<img src="https://i.imgur.com/RR6dl9A.png" height="100%" width="100%" alt="installation step"/>
</p>
<p>
-Navigate to: C:\inetpub\wwwroot\osTicket\include

-Right click on the "ost-config.php" file ->  click on "Properties" -> "Security" -> "Edit" -> under "Allow", check only the box for "Read".

This step enhances security after installing osTicket by deleting the setup folder to prevent reinstallation or unauthorized changes, and setting "Read-only" permissions on ost-config.php to protect critical configuration settings from modification.
</p>
<br />




<h2>osTicket Installed!</h2>

<b>Congratulations on installing osTicket from scratch!
In the next lab, we will dig deeper into the osTicket admin portal and configure various options such as SLAs, departments, permissions and access, agents, and more.</b>
<br />
<br />
</p>
