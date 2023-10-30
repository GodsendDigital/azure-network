<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>
https://i.imgur.com/n9YnKJ3.png
<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/n9YnKJ3.png" height="80%" width="80%" alt="D"/>
</p>
<p>
First step is to open up the Azure Portal and create a resource group. After the Resource Group is created, then proceed to create two Virtual Machines within the Resource Group. First Virtual Machine have the Windows 10 with 2 vCPU and 16gig of RAM installed on it. The second Virtual Machine has Linux (ubuntu 20.04) installed on it. Once the Virtual Machines is created, open up the Remote Desktop Protocol to run the VMs.
</p>
<br />

<p>
<img src="https://i.imgur.com/HD1uAjv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log into VM1 by using the IP Address and entering it into the RDP. Once I'm in, I download wireshark from the internet. Wireshark is an application that monitor internet traffic from all kinds of ports. I get on wireshark and bring up another app call powershell ise. Powershell ise allow users to use commands to create internet traffic inside wireshark. I begin to ping the IP address of the 2nd Virtual Machine through the ICMP port and the traffic is showing up in wireshark. Now I want to ping the VM2 IP Address non-stop and then block all incoming traffic from the ICMP Port.
</p>
<br />

<p>
<img src="https://i.imgur.com/5HQRK4v.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To block all incoming traffic from the ICMP, I have to go back into the Microsoft Azure Portal. Then go in the VM2 settings to access the Network Security Group that acts as a firewall. Once I am inside the Network Security Group I go to Inbound Traffic and create a rule to deny all inbound traffic from the ICMP to start the non-stop ping that I made a command to do in the powershell ise. The rule will stop all traffic and only show up as request time out in wireshark and powershell ise.
</p>
<br />

<img src="https://i.imgur.com/JcI3MSZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
I want to log in the VM2 via SSH from VM1 with powershell ise. In order to do that I bring up powershell ise and type the command "ssh username@ip address" then hit enter. My username is jumpman23 and private IP address of VM2 is 10.0.0.5 so I enter the command ssh jumpman23@10.0.0.5. Then I follow up with the password. Now I am log into the VM2 via SSH and I can use commands in powershell ise.
</p>
