<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket Prerequisites Setup Guide</h1>
This project is a comprehensive tutorial for setting up and installing the osTicket help desk ticketing system, including a detailed walkthrough of necessary configurations and installations.


<h2>Languages Used</h2>

- PowerShell

<h2>Environments Used:</h2>

- Microsoft Azure
- Windows 10
- Windows Server

<h2>Technologies/Applications/Services Used</h2>

- osTicket
- Azure Storage
- Azure Virtual Machines
<h2>Installation Steps: 1 - 12 (Create Virtual Environment) </h2>


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/0544afba-0aea-4fbc-af14-48bef245be3e)
<p>
Step 1: Navigate to "portal.azure.com/#home" to create a Resource Group. Search for Reasearh Groups. This group will house the Virtual Network and Subnet. 
</p>
<br />


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/cd72c54d-2bd4-4faf-aa2f-0e66cfe31066)
<p>
Step 2: Click "Create" to create the Resource Group
</p>
<br />


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/75dd74e0-5bdc-48b9-bfa0-3725503fb8aa)
<p>
Step 3: Name the resource group (ex: RGosTicket). Choose a region. Choose a region close to your primary user base to minimize latency. Also ensure that the region complies with local laws regarding data residency and privacy. Click Review + create.
</p>
<br />


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/c30940d2-6ddd-4a94-b56b-93251e7a675a)
<p>
Step 4: Search for Virtual Machines. Click Create. Select Azure virtual machine.
</p>
<br />


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/c4269b79-19f9-4746-9b22-743e7ab7d931)
<p>
Step 5: Select the Research Group we created (RGosTicket). Name the Virtual Machine (ex: vmOsTicket). Choose a Region (ex: (US) East US). Choose an image (ex: Windows 10 Pro, version 22H2 - x64 Gen2 (free services eligible)). 
</p>
<br />


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/a51d78e1-458d-403a-8f9e-5f7f164b6849)
![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/a3e38542-b06f-4247-b9d5-fc1673646370)
<p>
Step 6: Choose a size (ex: Standard_D4s_v3 - 4 vcpus, 16 GiB memory ($140.16/month)) note: limited subscriptions cannot use more than 4 vcpus. Choose a Username and Password (Username ex: jerryuser). Check the Licensing box, and click Next


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/b6f5b5bc-f0a2-4142-9533-f91dfa1c9815)
<p>
Step 7: Click Next again to navigate to Networking
</p>
<br />


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/a30a7ead-dc23-4b68-820c-f658cf0c5fc1)
<p>
Step 8: Azure will create a new Virtual Network and Subnet automatically (ex: (new)vmOsTicket-vnet / ex: (new)default(10.0.0.0/24)). Click Review + Create
</p>
<br />


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/edbb20ca-5790-41c5-8c67-9b6076f73e2e)
<p>
Step 9: Once Validation is passed. Click Create.
</p>
<br />


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/113e3ca2-6c80-4501-8669-54b7ceb84696)
<p>
Step 10: When deployment is complete. Navigate to Virtual Machines. Click the Virtual Machine name (ex: vmOsTicket) to see VM information.
</p>
<br />


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/5ee3dafc-4b46-4a98-9b19-f978e25bdd86)
<p>
Step 11: Copy the Public IP address(ex: 52.139.25.192). Open Remote Desktop Connection. Paste the Public IP address into bar. Click Connect.
</p>
<br />


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/502020cd-ed75-4e56-bfdd-a12d9d06d502)
<p>
Step 12: Enter Username/Password we created in Step 6 (Username ex: jerryuser). Click Continue.
</p>
<br />


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/fcdea7f8-7c50-49d9-82cb-62dcbd2b465c)
<p>
Screen should look similar to this.
</p>
<br />
<br />

<h2>Installation Steps: 13-47 (Installation of software dependencies & osTicket)</h2>


![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/0a15c7db-d223-4630-9bae-9715ee638db9)
![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/9baaba9e-c90b-41ab-94f7-a0c1428bc924)
<p>
Step 13: Right click the start menu and select "Run". Type 'control' and hit enter to open the Control Panel.
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/08f60fd5-04d4-46de-a5ba-3819d6aea187)
<p>
Step 14: Click "Programs"
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/ce876004-757b-4a21-91ca-23b67f7eca71)
<p>
Step 15: Click "Turn Windows features on or off"
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/d406b746-1315-4f87-a4e1-9adee48f2d0d)
<p>
Step 16: Check the box for "Internet Information Services"
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/2bc3a1d0-7e76-4aa6-9920-67888b063ee8)
<p>
Step 17: Expand "Internet Information Services". Expand "World Wide Web Services". Expand "Application Development Features". Check the box for "CGI"
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/0c7d42a6-8230-42ad-aa47-245d32d1276e)
<p>
Step 18: Collapse "Application Development Features". Expand "Common HTTP Features". Select all boxes and hit ok.
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/7a6deb13-bcce-4dd0-aabb-e54818873b6b)
<p>
Step 19: Ensure IIS enabling was successful by opening a browser. Enter 127.0.0.1 in the bar. Result should look like this.
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/45feffe3-aeeb-4e99-a897-aaacd44ab3cc)
<p>
Step 20: Download and install PHP manager
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/c0eb3d24-68de-4dac-872d-a17344e2ef77)
<p>
Step 21: Download and install the Rewrite Module (rewrite_amd64_en-US.msi)
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/b36a003b-c183-459e-a13e-4624d880773f)
<p>
Step 22: Navigate to C: drive from File Explorer. Create a new folder called PHP.
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/a4fce9ed-e76f-4e0f-99bd-631cbf2b0fc7)
<p>
Step 23: Download PHP. https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=share_link (php-7.3.8-nts-Win32-VC15-x86.zip). 
  Unzip the contents into C:\PHP 
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/54ced64d-67df-407c-abf1-e919dc2a32a8)
<p>
Step 24: Download and install C++ Redistributable 
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/affa7347-2351-4845-af47-87d3906359b4)
![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/79d4e63f-4cc1-4369-a8ea-b3328dd8ea13)
![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/5d85064d-735b-48b9-95cc-69ccdf16a859)
<p>
Step 25: Download and install MySQL Server. Choose Typical Setup. Choose Standard Configuration. Create a Password
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/2a190eb3-ba46-402b-a89c-f3c75c0976f6)
<p>
Step 26: Click Start. Type IIS. RIGHT-click Internet Information Services and choose "Run as Administrator"
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/04d9494f-aeeb-432d-9a3c-3be837121226)
<p>
Step 27: Double Click PHP Manager
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/b1eddda9-b6f7-4bec-8a5b-ed351133cbc3)
<p>
Step 28: Register new PHP version. Provide the path: "php-cgi" inside the PHP folder
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/9f735446-341a-4182-aae1-2a36821573f4)
<p>
Step 29: Click the server (ex: vmOsTicket(vmOsTicket\jerryuser)). Click "Restart" under Manage Server
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/6c202a69-d20c-438d-8323-e7bd879e5aa9)
Step 30: Download osTicket.(v1.15.8). Drag "upload" folder into c:\inetpub\wwwroot 
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/fe739ff0-eb8d-451c-b79f-3456a3806cef)
<p>
Step 31: Rename "upload" to "osTicket"
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/81ba5d5d-0035-4177-b72a-c23bdd875629)
<p>
Step 32: Click "Restart" inside of IIS
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/74f15c6a-1ecc-4682-a23d-9f402bedf495)
<p>
Step 33: Click the server (ex: vmOsTicket/jerryuser). Navigate to Sites -> Default Web Site -> click osTicket
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/6bd22125-56bf-4859-a2e9-49836c1d6022)
<p>
Step 34: Click Browse on the right side of IIS, then this window will open
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/e55e6ba8-a2da-4737-8391-d0dc6fc1f5c7)
<p>
Step 35: Double click PHP Manager. Click Enable or disable an extension
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/d1cca5c9-4592-4333-9d66-2f975300830b)
<p>
Step 36: Enable the following: php_imap.dll, php_intl.dll, php_opcache.dll - Refreshing browser should look like this. 
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/0f746d14-93c2-4880-8f71-5a1ade348b53)
<p>
Step 37: Navigate to ost-sampleconfig.php then rename this file ost-config.php
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/5c9e0fe4-f34d-4f48-91e5-f690dc963918)
<p>
Step 38: ost-config.php -> Properties -> Security -> Advanced -> Disable inheritance -> Remove all inherited permissions from this object
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/38e2484b-9985-4e07-a6e7-48c48af24c4f)
<p>
Step 39: Add -> Select a principal -> enter "everyone" in box -> Check Names -> click ok
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/ecb8b83a-6c45-49b4-bcd4-fcc78bc2f2c2)
<p>
Step 40: Give everyone full control -> Press Ok -> Apply -> Ok
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/98ddd229-e75c-42e0-9202-348746d26461)
<p>
Step 41: Click Continue on browser with osTicket open.
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/367aad7a-6f6a-475f-b679-22cc3664c168)
<p>
Step 42: Download and install Heidi SQL. https://www.heidisql.com/installers/HeidiSQL_12.3.0.6589_Setup.exe This will allow us to connect to the SQL server and set up a database that osTicket will use.
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/123bc8b9-d213-4211-a673-987f5f031dcc)
<p>
Step 43: Click New. Enter User(ex: root) and password. Click Open. This is the connection to the SQL server.
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/022af78f-6e5b-4195-9ef4-dbc2b581dc2b)
<p>
Step 44: Right click "Unnamed" and create a new Database called "osTicket"
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/44e0ab40-108e-48fc-ae63-b66dd3668a34)
![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/bd58517a-c665-45aa-a51f-cca58ba41102)
![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/21144164-602c-4590-9c23-690d373a9442)
<p>
Step 45: Fill out the osTicket installer form with the data you have chosen and click Install Now.
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/5a1931f1-5123-461c-905f-262bbef0d62f)
<p>
Step 46: Clean up. Navigate to This PC -> Windows(C:) -> inetpub -> wwwroot -> osTicket and delete the "setup" folder
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/3e27da98-7145-471e-9638-06f5eee573cb)
<p>
Step 47: Navigate to This PC -> Windows(C:) -> inetpub -> wwwroot -> osTicket -> include -> ost-config.php -> properties -> Security -> Advanced -> Click Everyone -> Edit -> Remove permissions: Full control, Modify, Write -> Ok -> Apply -> Ok -> Ok
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/9061f865-4a93-4fea-8e2b-2ee377ed3638)
<p>
Installation of osTicket is now complete!    
</p>
<p>

  URL for ADMIN: http://localhost/osTicket/scp/login.php
</p>
<p>
  URL for end users to create tickets: http://localhost/osTicket/
</p>
<br />

![image](https://github.com/kiesun01/osticket-prereqs/assets/132006466/034fc20d-6a45-48e7-b9b3-32279a729004)
<p>
LOGIN as ADMIN will display:
</p>
<br />
