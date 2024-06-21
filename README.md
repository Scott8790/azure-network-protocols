<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

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

- Create our Resources
- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DHCP Traffic
- Observe DNS Traffic
- Observe RDP Traffic

<h2>Actions and Observations</h2>

<img width="1313" alt="ANP2" src="https://github.com/Scott8790/azure-network-protocols/assets/172638339/45da78be-0778-46f2-8662-ede27bff47b0">

<p>
<img width="1268" alt="ANP1" src="https://github.com/Scott8790/azure-network-protocols/assets/172638339/bfcc1b06-9e71-4813-83d6-9a5b90b7643b">

</p>
<p>
Make a resource group in Azure and two separate VMs inside it. The first one will be a Windows 10 VM and the 2nd one will be a Linux Ubuntu VM. Install the program Wireshark onto the Windows VM so we can observe the traffic coming in and out
</p>
<br />

<p>
<img width="1287" alt="ANP3" src="https://github.com/Scott8790/azure-network-protocols/assets/172638339/31eb50c8-e0a2-4dcf-953b-4f8115cc5efa">

</p>
<p>
Open up Powershell on VM1 and ping the private IP address from VM2. They are able to communicate with each other because they are both on the same virtual network
</p>
<br />

<p>
<img width="1439" alt="ANP4" src="https://github.com/Scott8790/azure-network-protocols/assets/172638339/1a07782f-8632-4cc1-a0c2-f4f0bb73d124">

</p>
<p>
Within the Azure Portal, go to VM2 NSG(Network service group) and block incoming ICMP traffic by adding a new rule with higher priority. Once this is added we can now see the ICMP incoming traffic to VM2 is stopped because VM1 is no longer getting any replies from VM2 and Powershell keeps showing timed out
</p>
<br />

<p>
<img width="1663" alt="ANP5" src="https://github.com/Scott8790/azure-network-protocols/assets/172638339/13b978c1-ed51-434e-8c90-8d5e41571caf">

</p>
<p>
Set wireshark to only show ssh traffic. Using powershell, sign into VM2 with ssh @labuser10.0.0.5 command, type yes and then the password for the user account, then you see the welcome to Ubuntu message. We are now connected to VM2 through ssh via VM1. 10.0.0.5 is the private IP for VM2
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
