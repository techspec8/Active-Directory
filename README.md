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
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>Start by creating a Resource Group in Azure with a Domain Controller VM (Windows Server 2022) named “DC-1”, then a client VM using (Windows 10) named “Client-1”. Be sure to use the same Resource Group and Vnet that was created in DC-1.
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
Check connectivity between the Client and Domain Controller
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
