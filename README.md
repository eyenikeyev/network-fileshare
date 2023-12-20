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

<h3>Create Sample Fileshares with Permissions</h3>

</p>
Connect to Remote Desktop with the Domain Controller and log in as mydomain.com\jane_admin. Do the same with the Client vm and log in as a random user that was generated through the Powershell script in the Active Directory lab.
</p>
On Domain Controller vm, create 4 folders in the C:\ Drive and set the Permissions in these folders (by opening the folder's Properties and click on Share under the Sharing tab)
<p>

read-access: add the group Domain Users and set Permissions to Read
<p>
write-access: add the group Domain Users and set Permissions to Read/Write
<p>
no-access: add the group Domain Admins and set Permissions to Read\Write
<p>
accounting: skip for now
<p>
An Example of setting group and permissions
<p>
<img src="https://i.imgur.com/NgImT4S.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
</p>

<br/>

<h3>Attempt to Access Fileshares</h3>

<p>
On the Client vm go to the shared folder through file explorer and type \\dc-1
<p>
Attempt to access the folders, the only one that is inaccessible by the permissions set is no-access
<p>
<img src="https://i.imgur.com/Y3Y4tJN.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>

<br/>

<h3>Create a Security Group</h3>

<p>
Access Domain Controller vm, go to Server Manager and go to Active Directory Users and Computers. Create a new Organizational Unit and name it _security_group. Right click it and new group, name it accountants
<p>
<img src="https://i.imgur.com/RcrUU6l.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
Go to C:\ Drive, add the accountants group and set its permissions to Read\Write
<p>
<img src="https://i.imgur.com/5ALSXdu.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
The user logged in the Client vm should not have access to the accounting folder since its not part of the group. Log off and remember the username that was used to log into the Client, its going to be set as part of the accountants group
<p>
