<h1>Active Directory Lab</h1>

<p>Created a VM and domain using an external and internal NIC. Assigned IP addressing for the external network, and created Active Directory using NAT and DHCP. Used a PowerShell script to automate the creation of users. Then logged into another VM and joined it to the domain.</p>

<p>I first started by downloading and installing Oracle VirtualBox which I used to run the virtual machines on.</p>

<p>I then downloaded Windows 10 ISO and a Server 2019 ISO to install the Windows operating systems on 2 different virtual machines.</p>

<p>I then created my first virtual machine which housed Active Directory. I gave this virtual machine 2 network adapters: one for the outside internet and another for the internal private network that clients will connect to.</p>

<p>After the virtual machine was installed, I assigned Server 2019 onto it. Then I assigned IP addressing for the internal network. It automatically got IP addressing from the external network and home router.</p>

<p>I then named the server and installed Active Directory. Then we configured NAT and routing so clients can reach the server through the domain controller.</p>

<p>We then configured DHCP on the domain controller so clients are automatically assigned an IP address. When we create our Windows 10 machine, it will automatically get assigned an IP address.</p>

<p>I then executed a PowerShell script to automatically create 1000 users in Active Directory.</p>

<p>I created another virtual machine with Windows 10 on it, and that virtual machine was then connected to the private VirtualBox network.</p>

<p>First I installed VirtualBox, Windows 10 ISO, and Windows Server.</p>

<p>I allocated adequate RAM and CPU for the Domain Controller.</p>

<p>I then enabled 2 Network Adapters: one for the internal network and one for the external network.</p>

<p>I then started the Windows Server 2019 ISO to start the virtual machine.</p>

<p>I chose the selected version and launched the virtual machine.</p>

<p>Then I assigned a password to the Administrator account.</p>

<p>We booted into the VM and logged in as the administrator and we were in.</p>

<p>Then I set up the IP addressing and renamed each network adapter to specify between the internal and external networks.</p>

<p>Now that we have the internal and external NICs configured, the next step is to create a domain and use Active Directory Domain Services.</p>

<p>With Active Directory installed, we created a new forest.</p>

<p>We created an OU for Admin. We also created a domain admin account.</p>

<p>I then installed RAS / NAT to allow our client to be on our private virtual network but still access the public internet.</p>

<p>With our role installed, we configured routing and remote access.</p>

<p>We now have our domain set up.</p>

<p>We are now going to set up DHCP.</p>

<p>We named the server and assigned a scope.</p>

<p>We then assigned a scope and a lease duration.</p>

<p>We then added an IP address for the router used by the clients.</p>

<p>Great, now our DHCP server is set up!</p>

<p>We are then going to use the PowerShell script to make 1000 users.</p>

<p>We have 2 folders: one with 1000 names and the script folder.</p>

<p>I ran PowerShell ISE as an Administrator to run the PowerShell script. It uses the name folder to create users automatically.</p>

<p>It was a success! Now we are going to create the Windows 10 client and connect to the Domain Controller. We used <code>ipconfig</code> to ping the Domain Controller.</p>

<p>Finally, we pinged google.com to make sure the client is connected to the public internet.</p>

<p>And then we pinged our Domain Controller for good measure.</p>

<p>Great, everything is working as it should! This concludes the Active Directory Lab.</p>
