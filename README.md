<h1>Hi, I'm Brandon, an <a href="https://www.linkedin.com/in/brandon-buhr-136377304/">IT Professional</a>☺</h1>

<h2>🤳Connect with me:</h2>

[<img align="left" alt="Brandon | LinkedIn" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" />][linkedin]

[linkedin]: https://www.linkedin.com/in/brandon-buhr-136377304/
<br/>
<h1>Network File Shares and Permissions</h1>
This project uses two virtual machines to experiment with file shares and various permissions.

<h2>Languages and Utilities Used</h2>
<b>File Explorer</b>

<h2>Environments Used</h2>
<br/>
<b>Microsoft Azure</b>
<br/>
<b>Windows 10</b>
<br/>
<b>Windows Server</b>
<br/>

<h2>Walkthrough</h2>

<p align="center">
Create two virtual machines, one running Windows 10 (Client), the other running Windows Server (DC) <br/>
<br />
In DC, log in as a domain admin account and create four folders with various permissions: "read-access", "write-access", "no-access", "accounting"  <br/>
<img src="https://github.com/user-attachments/assets/9aa41489-cf68-4aad-8e9a-b5553c9b4127" height="80%" width="80%"/>
<br />
<br />
In Client, attempt to access file shares as a normal user: <br/>
<img src="https://github.com/user-attachments/assets/f61364ac-e332-44dc-b3cc-687831edd733" height="80%" width="80%"/>
<br />
<br />
Take note of which folders you can access and which you cannot:  <br/>
<img src="https://github.com/user-attachments/assets/49096b31-1a57-435f-8864-83c7ff3474b4" height="80%" width="80%"/>
<br />
<br />
In DC in Active Directory, create a security group called accountants:  <br/>
<img src="https://github.com/user-attachments/assets/094a4aad-dd9d-4ce2-8894-790225a62e45" height="80%" width="80%"/>
<br />
<br />
In the account folder created earlier, set these permissions: Group: “ACCOUNTANTS”, Permissions: “Read/Write” <br/>
<img src="https://github.com/user-attachments/assets/43d76d63-509c-499b-b3a7-c9f27d053fc7" height="80%" width="80%"/>
<br />
<br />
Log out of Client, then in DC, make a user a member of the "ACCOUNTANTS" Security Group <br/>
<img src="https://github.com/user-attachments/assets/a2dcfea7-f51c-446f-9328-24d0f0c9ef63" height="80%" width="80%"/>
  <br/>
Sign back into Client as the same user that was made a member of "ACCOUNTANTS" and try to access the "accounting" share. It should now work correctly.
