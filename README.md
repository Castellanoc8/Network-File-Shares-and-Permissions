<p align="center">
<img src="https://i.imgur.com/3vkYfAH.png"/>
</p>


<h1>Working with Network File Shares and Permissions</h1>
This tutorial outlines sharing resources over the network and creating file shares to allow Read, Write, or Deny access to individual users or groups.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Network File Shares
- Permissions

<h2>Operating Systems Used</h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High Level List of Steps</h2>

- Create some sample file shares with various permissions
- Attempt to access file shares as a normal user
- Create an "ACCOUNTANTS" Security Group, assign permissions, and test access.


<p>
<img src="https://i.imgur.com/k5Tg7hU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/N9UvEsD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/ZsCv0h4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/HqfQoMH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

In this tutorial, I worked with Network File Shares and Permissions. Also I used the same DC-1 and Client-1 Remote Desktops I created in the previous labs. First, I went into DC-1, and on the c:\drive, I created four new folders. I named these four new folders "read-access," "write-access," "no-access," and "accounting." Next, I had to set each folder's group to either "Domain Users" or "Domain Admins." Also, I had to set their permissions to either "Read" or "Read/Write." For the folder "read-access," I set the group to "Domain Users" with the permission "Read." After, for the folder "write-access," I set the group to "Domain Users" with the permission "Read/Write." And lastly, for the folder "no-access," I set the group to "Domain Admins" with the permission "Read/Write."
</p>
<br />

<p>
<img src="https://i.imgur.com/FCfdd3Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/cImTEaV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

In the next part of this tutorial, I attempted to access file shares as a Normal User. I did that by logging into Client-1 Remote Desktop and navigating to the shared folder (start, run, \\dc-1). While there, I went through each folder I previously created to see which folders I could access. Some of the folders allowed me in, while others blocked me out since I didn't have the permissions to access them.
</p>
<br />

<p>
<img src="https://i.imgur.com/Io9T9Lw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/1IDLxhi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/P16gW0I.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/aVqY2UW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
In the last step of this tutorial, I created a Security Group called "ACCOUNTANTS," assigned its permissions, and then tested its access. I did this by going into DC-1's Remote Desktop and returning to Active Directory. Here I created the "ACCOUNTANTS" Security group. Next, I went into the "accounting" folder I made in the first part of this lab and changed its group/permissions to the group "ACCOUNTANTS," and its permissions to "Read/Write." After doing that step, I went back into Client-1 and tried to access the accounts folder but had no success. There was no access at this point because I had not yet added a member to the "ACCOUNTANTS" security group yet. So to be able to access the "accounting folder," I had to first log out of Client-1's Remote Desktop and go back into DC-1. Once back in DC-1, I grabbed one of the random users accounts I made earlier in another tutorial and added that user to the "ACCOUNTANTS" security group. Lastly, I signed into Client-1's Remote Desktop with the random user account. I selected credentials for and tried to access the "accounting" folder. This time I successfully accessed the "accounting" folder since the random user account I was using had permission to access the folder.
</p>
<br />
