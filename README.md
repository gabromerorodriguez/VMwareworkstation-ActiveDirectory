<p align="center">
<img src="https://i.imgur.com/H7BNbwq.png" height="30%" width="15%" alt="VMware Workstation Logo"/>
</p>

<h1>Creating Network Diagrams, Building Servers and Configuring Group Policies</h1>
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
<strong>Inn of the Last Home</strong> is the domain of the network. The Virtual Machines named are Servera, Serverb, and Serverc. This network includes: two servers running Active Directory Domain Services (ADDS), two servers running DNS (the primary domain server and another server), one server running DHCP, two file and print servers, and one web server (IIS). The virtual machines
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

</p>
<br />
