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
- MySQL

<h2>Operating Systems Used </h2>

- Windows 10 Pro, version 22H2

<h2>High-LevelSteps</h2>

- Step 1: Create a Resource Group and a Virtual Machine
- Step 2: Connect to the Windows Virtual Machine
- Step 3: Download and Extract the osTicket installation folder
- Step 4: Install and Enable IIS with CGI
- Step 5: Install the PHP Manager
- Step 6: Install the Rewrite Module
- Step 7: Create a directory for PHP files
- Step 8: Unzip PHP files
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

<h3>Step 1: Create a Windows a Resource Group and a Virtual Machine</h3>
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

<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdfadsf
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdfasdf
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdfdassdf
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
adsfasdf
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
gasdg
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgadgs
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
adggads
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
adsgasdg
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdfgasdg
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgadgs
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgasdg
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgadg
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgasdg
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asgdgas
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
adgasdg
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgagds
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgasdg
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdggads
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asgasdg
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgagsd
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgasdg
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
agdgad
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdggad
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgasgd
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdggad
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asgdagsd
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgga
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgadgs
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgag
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgagds
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdggad
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdggad
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asgdadg
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgadgs
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdggda
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
adgag
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
asdgag
</p>
<br />


<p>
<img src="" height="100%" width="100%" alt="installation step"/>
</p>
<p>
aggads
</p>
<br />


<h2>osTicket Installed!</h2>

<b>Congratulations! osTicket is now officially installed and ready to use.
In the next lab, we will dig deeper into the osTicket helpdesk portal and configure various options such as SLAs, Departments, ... to complete.</b>
<br />
<br />
</p>
