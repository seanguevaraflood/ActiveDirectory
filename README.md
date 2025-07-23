<h1>Active Directory Lab</h1>

<p>Created a VM and domain using an external and internal NIC. Assigned IP addressing for the external network, and created Active Directory using NAT and DHCP. Used a PowerShell script to automate the creation of users. Then logged into another VM and joined it to the domain.</p>

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/b8278202bae6cf473e51ce01bfda9bb125e76803/images/Active%20Directory%20Diagram.png
)

<p>I first started by downloading and installing Oracle VirtualBox which I used to run the virtual machines on.</p>

<p>I then downloaded Windows 10 ISO and a Server 2019 ISO to install the Windows operating systems on 2 different virtual machines.</p>

<p>I then created my first virtual machine which housed Active Directory. I gave this virtual machine 2 network adapters: one for the outside internet and another for the internal private network that clients will connect to.</p>

<p>After the virtual machine was installed, I assigned Server 2019 onto it. Then I assigned IP addressing for the internal network. It automatically got IP addressing from the external network and home router.</p>

<p>I then named the server and installed Active Directory. Then we configured NAT and routing so clients can reach the server through the domain controller.</p>

<p>We then configured DHCP on the domain controller so clients are automatically assigned an IP address. When we create our Windows 10 machine, it will automatically get assigned an IP address.</p>

<p>I then executed a PowerShell script to automatically create 1000 users in Active Directory.</p>

<p>I created another virtual machine with Windows 10 on it, and that virtual machine was then connected to the private VirtualBox network.</p>

<p>First I installed VirtualBox, Windows 10 ISO, and Windows Server.</p>

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/b8278202bae6cf473e51ce01bfda9bb125e76803/images/Active%20Directory%20Diagram.png
)

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/b8278202bae6cf473e51ce01bfda9bb125e76803/images/Virtual%20Box%20Download.png
)


![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/aac12401109d4b83a8cce5fcdaec85727ea1fce7/images/Windows%2010%20Download.png
)

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/aac12401109d4b83a8cce5fcdaec85727ea1fce7/images/Windows%20Server%20Download.png
)

<p>I allocated adequate RAM and CPU for the Domain Controller.</p>

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/b8278202bae6cf473e51ce01bfda9bb125e76803/images/Ram%20Allocation.png
)

<p>I then enabled 2 Network Adapters: one for the internal network and one for the external network.</p>

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/aac12401109d4b83a8cce5fcdaec85727ea1fce7/images/Network%20Connection%201.png
)

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/aac12401109d4b83a8cce5fcdaec85727ea1fce7/images/Network%20Connection%202.png
)

<p>I then started the Windows Server 2019 ISO to start the virtual machine.</p>

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/aac12401109d4b83a8cce5fcdaec85727ea1fce7/images/Windows%20Server%20Start%201.png
)

<p>I chose the selected version and launched the virtual machine.</p>

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/aac12401109d4b83a8cce5fcdaec85727ea1fce7/images/Windows%20Server%20Start%202.png
)

<p>Then I assigned a password to the Administrator account.</p>

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/aac12401109d4b83a8cce5fcdaec85727ea1fce7/images/Windows%20Server%20Admin%20Log%20In.png
)

<p>We booted into the VM and logged in as the administrator and we were in.</p>

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/5f56eba916814a4b00253fe0e060ffadd9e1f941/images/Windows%20Server%20Start.png
)

<p>Then I set up the IP addressing and renamed each network adapter to specify between the internal and external networks.</p>

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/5f56eba916814a4b00253fe0e060ffadd9e1f941/images/IP%20Addressing.png
)

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/5f56eba916814a4b00253fe0e060ffadd9e1f941/images/Network%20Connection%201.png
)

![image alt](https://github.com/seanguevaraflood/ActiveDirectory/blob/5f56eba916814a4b00253fe0e060ffadd9e1f941/images/Network%20Connection%202.png
)

<p>Now that we have the internal and external NICs configured, the next step is to create a domain and use Active Directory Domain Services.</p>

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5f56eba916814a4b00253fe0e060ffadd9e1f941/images/Select%20Server%20Roles.png
)

<p>With Active Directory installed, we created a new forest.</p>

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5f56eba916814a4b00253fe0e060ffadd9e1f941/images/Deployment%20Configuration.png
)

<p>We created an OU for Admin. We also created a domain admin account.</p>

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5f56eba916814a4b00253fe0e060ffadd9e1f941/images/Organizational%20Unit%20For%20Admin.png
)


<p>I then installed RAS / NAT to allow our client to be on our private virtual network but still access the public internet.</p>


![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/fab287e0d729956a401b5a6a548df01b4ab621ca/images/Server%20Roles%20RAS.png
)

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/9c39ab4e3cff0fbfd1c60c208e2f68c1a7c6a29e/images/Select%20Role%20Services.png
)

<p>With our role installed, we configured routing and remote access.</p>


![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5380893ae44efdf62020937b3afc5874d7a1fad6/images/NAT%20Set%20Up.png
)

<p>We now have our domain set up.</p>

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5380893ae44efdf62020937b3afc5874d7a1fad6/images/Domain%20Set%20Up.png
)

<p>We are now going to set up DHCP.</p>

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5380893ae44efdf62020937b3afc5874d7a1fad6/images/DHCP%20Set%20Up%201.png
)

<p>We named the server and assigned a scope.</p>

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5380893ae44efdf62020937b3afc5874d7a1fad6/images/DHCP%20Set%20Up%202.png
)

<p>We then assigned a scope and a lease duration.</p>

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5380893ae44efdf62020937b3afc5874d7a1fad6/images/DHCP%20Set%20Up%203.png
)

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5380893ae44efdf62020937b3afc5874d7a1fad6/images/DCHP%20Set%20Up%204.png
)

<p>We then added an IP address for the router used by the clients.</p>

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5380893ae44efdf62020937b3afc5874d7a1fad6/images/DCHP%20Set%20Up%205.png
)


![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5380893ae44efdf62020937b3afc5874d7a1fad6/images/DNS%20Set%20Up.png
)

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5380893ae44efdf62020937b3afc5874d7a1fad6/images/DCHP%206.png
)

<p>Great, now our DHCP server is set up!</p>

<p>We are then going to use the PowerShell script to make 1000 users.</p>

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5380893ae44efdf62020937b3afc5874d7a1fad6/images/Powershell%20Script%201.png
)


<p>We have 2 folders: one with 1000 names and the script folder.</p>

<p>I ran PowerShell ISE as an Administrator to run the PowerShell script. It uses the name folder to create users automatically.</p>

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5380893ae44efdf62020937b3afc5874d7a1fad6/images/Powerscript%202.png
)

<p>It was a success! Now we are going to create the Windows 10 client and connect to the Domain Controller. We used <code>ipconfig</code> to ping the Domain Controller.</p>

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/5380893ae44efdf62020937b3afc5874d7a1fad6/images/Windows%20Client%20Set%20Up%201.png)

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/182f16bb742f6717c1d1f42231f8db70b814d27c/images/Windows%20Client%20Set%20Up%202.png)


![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/182f16bb742f6717c1d1f42231f8db70b814d27c/images/Windows%20Client%20Set%20Up%203.png)

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/182f16bb742f6717c1d1f42231f8db70b814d27c/images/Windows%20Client%20Set%20Up%204.png)


<p>Finally, we pinged google.com to make sure the client is connected to the public internet.</p>

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/182f16bb742f6717c1d1f42231f8db70b814d27c/images/Ping%201.png
)

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/182f16bb742f6717c1d1f42231f8db70b814d27c/images/Ping%202.png
)

<p>And then we pinged our Domain Controller for good measure.</p>

![image alt](
https://github.com/seanguevaraflood/ActiveDirectory/blob/182f16bb742f6717c1d1f42231f8db70b814d27c/images/Ping%203.png
)

<p>Great, everything is working as it should! This concludes the Active Directory Lab.</p>
