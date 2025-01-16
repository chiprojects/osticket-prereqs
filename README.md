<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Full Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://youtu.be/OSTgG3tRP6Q?si=JL2NbKHvSpbVbYmF)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Windows Virtual Machine
- Web Server:IIS with CGI
- PHP Manager
- MYSQL
- VC (Visual C++) Redistributable
- Rewrite Module
- HeidiSQL

<h2>Installation Steps</h2>

<h3>Create Windows Virtual Machine in Azure</h3> (ENDS 13:29)

[![Video Title](https://img.youtube.com/vi/OSTgG3tRP6Q/0.jpg)](https://youtu.be/OSTgG3tRP6Q?start=000&amp;end=525;si=4RNq_shzXTkBosSz)

<b>1)Create a resource group by typing `Resource Group` in the search bar or selecting `Resource Group` on the Azure homepage</b>
<p>
<img src="https://github.com/user-attachments/assets/f73e5b27-d09e-4a42-8cf5-cd54d38083be" height="80%" width="80%" alt="Creating Resource Group Steps"/>
</p>

Fill in the following fields under the `Basics` tab:

   - `Subscription`
   - `Resource Group`
   - `Region`

Once everything is filled out select `Create` on the bottom left of your page to create the `Resource Group` aka 'folder' in which the virtual machine will be created in.

<p>
  <img src="https://github.com/user-attachments/assets/5c4ac609-bc87-499d-b9a7-1455f17907f6" height="80%" width="40%" alt="Creating Resource Group Steps"/> &emsp; &emsp;
  <img src="https://github.com/user-attachments/assets/9090386b-9bf5-4414-9ece-2e44888d81d3" height="80%" width="40%" alt="Creating Resource Group Steps"/>
</p>


<p>
<b>2)Create a Windows 10 virtual machine(Version 22H2) within the newly created 'Resource Group' by selecting `Virtual Machine` on the homepage or typing `VM` in the search bar.</b>
</p>
<p>
 <img src="https://github.com/user-attachments/assets/edc91528-9a80-4e58-8658-8767206bfaef" height="80%" width="80%" alt="Creating Resource Group Steps"/>
</p>

Fill in the following fields under the 'Basics' Tab: 

   - `Subscription`
   - `Resource Group`
   - `Region`
   - `Availability Zone`
   - `Image`
   - `Size`: Select `2vcpus` for the best balance between VM performance and stability
   - `All Administrative account fields`

<p>
  <img src="https://github.com/user-attachments/assets/757eb74b-8b2f-478d-a088-235367b060f0" height="80%" width="35%" alt="Creating a Virtual Machine"/>
  <img src="https://github.com/user-attachments/assets/36045603-f793-4891-9af8-cb5bb7eec961" height="80%" width="35%" alt="Creating a Virtual Machine"/>
  <img src="https://github.com/user-attachments/assets/948858b3-6a68-486e-922f-b7921c0acc2b" height="80%" width="35%" alt="Creating a Virtual Machine"/>
  
</p>

Skip over the `Disk` tab and navigate to the `Networking` tab where you can rename the virtual network or leave as is. <strong>`Note`:</strong> Everytime a virtual machine is created in Azure, a virtual network is configured. Continue to select `Review & Create` until you see `Create` on the bottom right corner. Wait for the virtual machine to deploy.

<img src="https://github.com/user-attachments/assets/c13df216-e678-4eea-afe3-a644f1e09a95" height="80%" width="80%" alt="Creating a Virtual Machine"/>


<h3>Assess the Virtual Machine</h3> (Starts 13:24 / Ends: 15:44)

[![Video Title](https://img.youtube.com/vi/OSTgG3tRP6Q/0.jpg)](https://youtu.be/OSTgG3tRP6Q?si=H5XNvBKvTDNT6KHt&t=805)

<br>1) Open up Remote Desktop Connection</br>

For Mac Users: Download and install the <a href="https://apps.apple.com/us/app/windows-app/id1295203466?mt=12">`Windows App`</a>

Copy the public IP address from the Overview tab of the virual machine dashboard and paste in the `Computer` field of the `Remote Desktop Connection`


![image](https://github.com/user-attachments/assets/efe6d927-2af9-4343-9a29-9be526e674af)

![image](https://github.com/user-attachments/assets/f3120a6c-5306-4801-8594-e9352fb876b0)


Enter the administrative account credentials created earlier in Azure when setting up the virtual machine and select okay. You're now logged into your remote session🙌🏾

![image](https://github.com/user-attachments/assets/1136f7c4-cd82-44d5-9dd9-38474c994391)


<h3>Download and Prepare OS-Ticket Installation Files</h3> (Starts:17:43 / End:19:16)

[![Video Title](https://img.youtube.com/vi/OSTgG3tRP6Q/0.jpg)](https://youtu.be/OSTgG3tRP6Q?si=ASNgp2CMuQ2tm0p6&t=1063)

<b>1) Within the virtual machine, download the `osTicket-Installation-Files.zip` and unzip it to your desktop </b>

![image](https://github.com/user-attachments/assets/f462fd3c-dfd5-44c2-a11c-ebfe3ee961a2)

<strong> Note:</strong> Notice the distinction between the unzipped and zipped folder:

![image](https://github.com/user-attachments/assets/9003a851-4e50-41ed-a428-e0205cd8523f)

<h3>Install/Enable IIS: Internet Information Services with CGI: Common Gateway Interface </h3>(Starts: 20:30 / Ends: 22:40)

[![Video Title](https://img.youtube.com/vi/OSTgG3tRP6Q/0.jpg)](https://youtu.be/OSTgG3tRP6Q?si=DepU3uh_c-5gtg78&t=1230)

<b>1) Install IIS and Enable Required Features</b>

Within the `VM`, select the `Start` menu: <img src="https://github.com/user-attachments/assets/2cefedd8-2966-4817-ae8d-3ae3eee68ba5" height="3%" width="3%" alt="Windows Start Menu"/> and navigate to the following:

> Control Panel > Programs > <u>Programs & Features</u>: `Turn Windows features on and off`

Install IIS with CGI with the following features:
`Internet Information Services` > World Wide Web Services > Application Development Features > `CGI`

![image](https://github.com/user-attachments/assets/ab6e5d7d-0b59-4060-aa59-725e5db96df9)

<h3>Install PHP Manager and Rewrite Module</h3> (Starts: 23:02 / Ends: 24:33)

[![Video Title](https://img.youtube.com/vi/OSTgG3tRP6Q/0.jpg)](https://youtu.be/OSTgG3tRP6Q?si=rNhBY1RWhI0cvSh3&t=1382)


<b>1)Install Required osTicket Components</b>

Navigate to the `osTicket-Installation-Files` folder on your desktop and select `PHPManagerForIIS_V1.5.0.msi` and then later `rewrite_amd64_en-US.msi`for installation.

![image](https://github.com/user-attachments/assets/34ca727f-cac8-4c92-a060-abcfdbd46172)

<h3>Setup PHP</h3> (Starts: 24:39 / Ends: 28:14)

[![Video Title](https://img.youtube.com/vi/OSTgG3tRP6Q/0.jpg)](https://youtu.be/OSTgG3tRP6Q?si=D2oG1STS6cBcHuIl&t=1479)

<b>1) Create a C:\PHP directory</b>

Navigate to the VM's `C:/` folder and create a new sub-folder named `PHP`. From the `osTicket-Installation-Files` folder, right-click on `PHP 7.3.8: php-7.3.8-nts-Win32-VC15-x86.zip` to extract all files into `C:/PHP`.

![image](https://github.com/user-attachments/assets/d4a787df-c90a-4661-b30a-2f02cdf2f156)

![image](https://github.com/user-attachments/assets/f7520fbd-ae60-4789-ad18-651daa13ba4e)

<b>1)Install Visual C++ Redistributable </b>

Install `VC_redist.x86.exe` from the `osTicket-Installation-Files` folder

![image](https://github.com/user-attachments/assets/da4cdede-9bae-4c7c-b2ef-10ba7e03bd08)

<h3>Install mySQL</h3> (Starts: 28:34 / Ends: 31:28 )

[![Video Title](https://img.youtube.com/vi/OSTgG3tRP6Q/0.jpg)](https://youtu.be/OSTgG3tRP6Q?si=WXHTYIJ5K79RP_Os&t=1714)

<b>1)Install mySQL Typical Setup</b>

Navigate to `osTicket-Installation-Files` folder and install MySQL 5.5.62: `mysql-5.5.62-win32.msi` > Choose Setup Type: choose <b>Typical Setup</b>.

Once the installation is complete, the Configuration Wizard should automatically launch
 >Select 'Standard Configuration' and input a username and password that will be used to access the database later on.


![image](https://github.com/user-attachments/assets/fd96cebf-c8b8-4e1d-b2c3-baa877f43650)


<h3>Configure IIS</h3> (Starts: 32:05  / Ends: 35:14 )

[![Video Title](https://img.youtube.com/vi/OSTgG3tRP6Q/0.jpg)](https://youtu.be/OSTgG3tRP6Q?si=UwKe-Lt8VPzwr6EO&t=1925)

<b>1)Open `IIS` as an Admin</b>

Within the `VM` select the `Start` menu: <img src="https://github.com/user-attachments/assets/2cefedd8-2966-4817-ae8d-3ae3eee68ba5" height="3%" width="3%" alt="Windows Start Menu"/> and type `Internet Information Services`

![image](https://github.com/user-attachments/assets/20ba1633-4529-4911-b8e5-27e71f03f519)

<b>2)Register PHP</b>
 
Select `PHP Manager` on the home menu > Register New PHP Version > Select path: `C:\PHP\php-cgi.exe`

![image](https://github.com/user-attachments/assets/5a364f0f-e865-4b20-9ac0-146a3b6d5ed4)

<b>3)Reload IIS</b>

`Stop` and `Start` the server

![image](https://github.com/user-attachments/assets/b1f06493-2769-4774-8b7a-b8abf905077d)

<h3>Install osTicket</h3> (Starts: 35:15  / Ends: 39:12 )

[![Video Title](https://img.youtube.com/vi/OSTgG3tRP6Q/0.jpg)](https://youtu.be/OSTgG3tRP6Q?si=0lnTDM1AlVwn-Eci&t=2115)

<b>1)Install `osTicket v1.15.8`</b>

From the `osTicket-Installation-Files` folder unzip `osTicket-v1.15.8.zip` and copy the `upload` folder into `C:\inetpub\wwwroot`. Now rename the `upload` folder `osTicket`

![image](https://github.com/user-attachments/assets/7a4194b9-076a-4463-beda-74e9ed5b5dc7)

<b>2)Reload IIS</b>

`Stop` and `Start` the server

![image](https://github.com/user-attachments/assets/bf3bdbfe-fb60-4316-9f6d-0ce5667cc920)

<h3>Configure osTicket</h3> (Starts: 45:03  / Ends: )

[![Video Title](https://img.youtube.com/vi/OSTgG3tRP6Q/0.jpg)](https://youtu.be/OSTgG3tRP6Q?si=eiBOqEK14c_zxCmm&t=2703)

<b>1)Enable Required Extenstions </b>












<p>
<img src="blank.jpg" height="250" width="500" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="40%" alt="Virtual Machine"/>
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
