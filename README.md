<p align="center">
<img src="https://github.com/ColtonTrauCC/network-fileshare/assets/147654000/efe94bff-a469-4342-a4c6-e927befd13b9" height = 20% width = 20%/>
</p>

<h1 align = "center">Network Fileshare and Permissions</h1>
File sharing and permissions set up is a structure in order to organize resources and make sure users have the appropriate permissions and access to files they need.
<br />

<h2>Environments and Technologies Used</h2>
<ul>
  <li>Microsoft Azure (Virtual Machines/Compute)</li>
  <li>Remote Desktop</li>
  <li>Active Directory Domain Services</li>
</ul>

<br />

<h2>Operating Systems Used</h2>
<ul>
  <li>Windows Server 2022</li>
  <li>Windows 10 Pro (21H2)</li>
</ul>

<br />

<h2>Steps</h2>

<h3>Creating Sample Fileshares with Permissions</h3>

</p>
  <ul>
Connect to Remote Desktop with the Domain Controller and log in as mydomain.com\jane_admin. Do the same with the Client vm and log in as a random user that was generated through the Powershell script in the Active Directory lab.
</p>
On Domain Controller vm, create 4 folders in the C:\ Drive and set the Permissions in these folders (by opening the folder's Properties and click on Share under the Sharing tab)
</p>
read-acess: add the group Domain Users and set Permissions to Read
<p>
write-access: add the group Domain Users and set Permissions to Read/Write
<p>
no-access: add the group Domain Admins and set Permissions to Read\Write
<p>
accounting: skip for now
<p>
