<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- Command Prompt

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create Domain Controller and Client Virtual Machines in Azure
- Configure Network Interface (NIC) 
- Check Connectivity between VM's
- Enable ICMPv4 on Server
- Configure and Install Active Directory
- Create User Accounts in AD
- Connect Client-1 to DNS Server
- Join Client-1 to mydomain.com
- Setup Remote User Access


<h2>Deployment and Configuration Steps</h2>

<b>Start by creating a Resource Group in Azure with a Domain Controller VM (Windows Server 2022) named “DC-1”, then a client VM using (Windows 10) named “Client-1”. Be sure you're using the same Vnet/Subnet that was created in DC-1.
</b>
<p>
<img src= https://i.imgur.com/KZXdOjx.png
</p>
<br />
<br />

<b>
Configure Domain Controller’s NIC Private IP address from Dynamic to Static. 
</b>
<p>
<img src= https://i.imgur.com/7cE7bS2.png
</p>
<p>
<img src= https://i.imgur.com/H9U55Mx.png
</p>
<p>
<img src= https://i.imgur.com/ZPdQLUx.png
</p>
<br />
<br />
  
<b>
Check connectivity between the Client and Domain Controller. Login to Client-1 with Remote Desktop and ping DC-1’s private IP address with a perpetual ping -t <ip address> observe that your request timed out and the connection failed.  
</b>
<p>
<img src= https://i.imgur.com/wbdOrHN.png
</p>
<br />
<br />
  
<b>
Remotely log into Domain Controller to enable ICMPv4 in Windows Defender Firewall with Advanced Security; Inbound Rules (filter Protocol for ICMPv4, the protocol Ping uses);Enable Core Networking Diagnostics Echo; Observe Successful Connectivity from Client Desktop  
</b>
<p>
<img src= https://i.imgur.com/P9wpgxA.png
</p>
<p>
<img src= https://i.imgur.com/LNnurWM.png
</p>
<p>
<img src= https://i.imgur.com/5BuoQae.png
</p>
<br/>
<br />

<b>
Install Active Directory on the Server Manager Dashboard from Add Roles and Features; setup a new forest as mydomain.com; restart and log back into DC-1 as user: mydomain.com\labuser
</b>
<p>
<img src= https://i.imgur.com/I5Ii8dQ.png
</p>
<p>
<img src= https://i.imgur.com/FP1YnxS.png
</p>
<p>
<img src= https://i.imgur.com/WhHpZ5A.png
</p>
<p>
<img src= https://i.imgur.com/quXQbsF.png
</p>
<br/>
<br />

<b>
In Active Directory Users and Computers, create two new Organizational Units under mydomain.com, EMPLOYEES, and ADMINS. Create a new user jane_admin in the ADMINS Organizational Unit. Next, add jane_admin to the “Domain Admins” Security Group. Log out and back in as jane_admin. 
</b>
<p>
<img src= https://i.imgur.com/QmTD3gb.png
</p>
<p>
<img src= https://i.imgur.com/CIrE301.png
</p>
<p>
<img src= https://i.imgur.com/UfzHn0p.png
</p>
<p>
<img src= https://i.imgur.com/kw6rDYC.png
</p>
<br/>
<br />

<b>
Change Client-1’s NIC DNS settings to DC’s Private IP from Azure. Open Client-1; Network Settings; Network Interface; DNS Servers: select Custom; insert DC-1's Private IP and Save; Restart Client-1. Log back into Client-1's Remote Desktop and confirm connection to DC-1's Private IP under DNS Server using Command Prompt ipconfig /all. 
</b>
<p>
<img src= https://i.imgur.com/4Fdhhhy.png
</p>
<p> 
<img src = https://i.imgur.com/ZEu1MGq.png 
</p>
<p> 
<img src = https://i.imgur.com/ZEu1MGq.png 
</p>
<br/>
<br />

<b>Join Client-1 to your domain (mydomain.com). Right click start menu; System; Rename this PC (Advanced); Change; Select Domain and enter mydomain.com; enter jane_admin's credentials. Client-1 will be prompted to restart.
</b>
<p> 
<img src = https://i.imgur.com/mn2ztCB.png
</p>
<p> 
<img src = https://i.imgur.com/5lAVMJO.png <p><img src = https://i.imgur.com/tmEStI6.png
</p>
<br />
<br />

<b>To set up remote users by security group, log into Client-1 as jane_dmin, open System Properties from start menu. Click “Select users that can remotely access this PC”. Click “Add”, then select the security groups you want to add. You can now log into Client-1 as a normal, non-administrative user now.  
</b>
<p> 
<img src = https://i.imgur.com/fSkjG94.png <p><img src= https://i.imgur.com/kjIk9TT.png
</p>
<br />
<br />
