<p align="center">
<img src="https://i.imgur.com/H7BNbwq.png" height="30%" width="15%" alt="VMware Workstation Logo"/>
</p>

<h1>Creating Network and Active Directory Diagrams, Building Servers and Configuring Group Policies</h1>
This tutorial outlines the implementation of Active Directory and Group Policy Objects (GPOs) to streamline administrative tasks and enforce centralized management policies within VMware Workstation virtual machines.<br />


<h2>Environments and Technologies Used</h2>

- VMware Workstation 16 Pro
- Active Directory Domain Services
- Microsoft Visio 

<h2>Operating Systems Used </h2>

- Windows Server 2016
- Windows 10 (21H2)

<h2>Configuration Steps</h2>

- Create network and active directory diagrams using Microsoft Visio
- Build active directory and file servers
- Configuration of Group Policies

<h2>Create network and active directory diagrams using Microsoft Visio</h2>

<h3>Nerwork Diagram</h3>
<p>
<img src="https://i.imgur.com/1B21jeX.jpeg" height="80%" width="80%" alt="Network Diagram"/>
</p>
<p>
<strong>Inn of the Last Home</strong> is the domain of the network. The Virtual Machines named are Servera, Serverb, and Serverc. This network includes: two servers running Active Directory Domain Services (ADDS), two servers running DNS (the primary domain server and another server), one server running DHCP, two file and print servers, and one web server (IIS).
</p>
<br />

<h3>Active Directory Diagram</h3>
<p>
<img src="https://i.imgur.com/ybagezd.jpeg" height="80%" width="50%" alt="Active Directory Diagram"/>
</p>
<p>
The Active Directory Diagram shows all Organizational Units (OU's), Users and Groups. We grouped people with similar job responsabilities together to later apply the permissions. In this case, we have the Character and Dragons Groups and every member has its name and username displayed. 
</p>
<br />

<h2>Build active directory and file servers</h2>

<h3>Active Directory Server</h3>

<p>
<img src="https://i.imgur.com/rAYtCKR.png" height="80%" width="80%" alt="Windows Server 2016 "/>
</p>
<p>
We started by creating the Virtual Machine "Servera" with Windows Server 2016 and installed the role of Active Directory Domain Services (ADDS). 
</p>
<br />

<p>
<img src="https://i.imgur.com/TvcLe9f.png" height="80%" width="80%" alt="AD Diagram"/>
<img src="https://i.imgur.com/YsRnmyy.png" height="80%" width="80%" alt="AD Diagram"/>
</p>
<p>
We created all the OU's, Users and Groups as documented from our AD diagram. 
</p>
<br />

<h3>File Server</h3>

<p>
<img src="https://i.imgur.com/uU5uvZ4.png" height="80%" width="80%" alt="File Server"/>
</p>
<p>
We produced a new server "Serverb" with Windows server 2016 and file server. Then we added the role of File Resource Manager. Serverb is joined to the domain but we did not promote it. 
</p>
<br />

<p>
<img src="https://i.imgur.com/2kiVEO0.png" height="80%" width="80%" alt="File Server"/>
<img src="https://i.imgur.com/WJmaK65.png" height="80%" width="60%" alt="File Server"/>
<img src="https://i.imgur.com/3aIlGBR.png" height="80%" width="60%" alt="File Server"/>
</p>
<p>
Inside Serverb, on File and Storage Services is located the Shares section, in the Shares section we created a shared folder for each OU's and added to additonal shares: Public and Home. The we shared the folders and in terms of permissions, we added the respecive groups with full control to each of them. Lastly, we configured and redirected users from home folder to the home share. In the last picture, Servera is able to access to the folder "Testing Redirect Folder" created on Serverb. 
</p>
<br />

<h3>Configuration of Group Policies</h3>
<p>
We created a Windows 10 desktop client to test the settings as a user.
</p>
<br />

<p>
<img src="https://i.imgur.com/Ej5L9o3.png" height="80%" width="80%" alt="Group Policies"/>
<img src="https://i.imgur.com/g0zPTOs.png" height="80%" width="80%" alt="Group Policies"/>
</p>
<p>
To disable the command prompt using Group Policy Objects (GPOs), we first accessed the Group Policy Management Console (GPMC) on a domain-joined Windows server, in this case, the Servera. Next, we navigated to the desired organizational unit (OU) or domain in the GPMC and created a new GPO. Within the Group Policy Management Editor, we navigated to User Configuration > Administrative Templates > System. Here, we located the policy setting named "Prevent access to the command prompt" and double-clicked to modify it. We then set the policy to "Enabled" to prevent users from accessing the command prompt. After applying the changes, we ensured that the GPO is linked to the appropriate OU and domain. Finally, we forced a Group Policy update on client computer if immediate enforcement is required. This process effectively disables the command prompt for users within the specified scope of the GPO, helping to enforce security policies and prevent unauthorized command execution.
<br />

<p>
<img src="https://i.imgur.com/LiYs4xe.png" height="80%" width="80%" alt="Group Policies"/>
<img src="https://i.imgur.com/6oAQvX9.png" height="80%" width="80%" alt="Group Policies"/>
</p>
<p>
To list limited allowed Control Panel items using Group Policy Objects (GPOs) within the Group Policy Management Editor, we navigated to User Configuration > Administrative Templates > Control Panel. Here, we located the policy setting named "Show only specified Control Panel items" and double-click to modify it. We then set the policy to "Enabled" and added the list of Control Panel items that we want to allow users to access. After applying the changes, we ensure that the GPO is linked to the appropriate OU or domain. 
<br />
