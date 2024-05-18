<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create Resources in Azure
- Configure Network Interface (NIC) 
- Check Connectivity between VM's
- Enable ICMPv4 on Server
- Install Active Directory

<h2>Deployment and Configuration Steps</h2>

<p>Start by creating a Resource Group in Azure with a Domain Controller VM (Windows Server 2022) named “DC-1”, then a client VM using (Windows 10) named “Client-1”. Be sure you're using the same Vnet/Subnet that was created in DC-1.
<p>
<img src= https://i.imgur.com/KZXdOjx.png
</p>
<br />

<p>
Configure Domain Controller’s NIC Private IP address from Dynamic to Static. 
</p>
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

<p>
Check connectivity between the Client and Domain Controller. Login to Client-1 with Remote Desktop and ping DC-1’s private IP address with a perpetual ping -t <ip address> observe that your request timed out and the connection failed.  
</p>
<p>
<img src= https://i.imgur.com/wbdOrHN.png
</p>
<br />

<p>
Remotely log into Domain Controller to enable ICMPv4 in Windows Defender Firewall with Advanced Security; Inbound Rules (filter Protocol for ICMPv4, the protocol Ping uses);Enable Core Networking Diagnostics Echo; Observe Successful Connectivity from Client Desktop  
</p>
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

<p>
Install Active Directory on the Server Manager Dashboard from Add Roles and Features; setup a new forest as mydomain.com; restart and log back into DC-1 as user: mydomain.com\labuser; 
</p>
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

<p>
Install Active Directory on the Server Manager Dashboard from Add Roles and Features; setup a new forest as mydomain.com; restart and log back into DC-1 as user: mydomain.com\labuser; 
</p>
<p>
<img src= https://i.imgur.com/I5Ii8dQ.png
</p>
<p>
<img src= 
</p>
<p>
<img src= 
</p>
<p>
<img src= 
</p>
<p>
<img src= 
</p>
<br/>
