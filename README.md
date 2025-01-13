<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

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
  <img src="https://github.com/user-attachments/assets/757eb74b-8b2f-478d-a088-235367b060f0" height="80%" width="35%" alt="Creating Resource Group Steps"/>
  <img src="https://github.com/user-attachments/assets/36045603-f793-4891-9af8-cb5bb7eec961" height="80%" width="35%" alt="Creating Resource Group Steps"/>
  <img src="https://github.com/user-attachments/assets/948858b3-6a68-486e-922f-b7921c0acc2b" height="80%" width="35%" alt="Creating Resource Group Steps"/>
  
</p>

Skip over the `Disk` and navigate to the `Networking` tab where you can rename your virtual network or leave as is. <strong>`Note`:</strong> Everytime a virtual machine is created in Azure, a virtual network is configured 





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
