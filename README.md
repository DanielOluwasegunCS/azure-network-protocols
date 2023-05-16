<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

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

- Create our Resources in Microsoft Azure:

      - Create a Resource Group
      - Create a Windows 10 Virtual Machine (VM)
      - Create a Linux (Ubuntu) VM

- Observe ICMP Traffic:

      - Use Remote Desktop to connect to your Windows 10 Virtual Machine
      - Within your Windows 10 Virtual Machine, Install Wireshark
      - Open Wireshark and filter for ICMP traffic only
      - Retrieve the private IP address of the Ubuntu VM and attempt to ping it from within the Windows 10 VM
      - From The Windows 10 VM, open PowerShell and attempt to ping a public website (such as www.google.com) and observe the traffic in Wireshark
      - Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM
      - Open the Network Security Group your Ubuntu VM is using and disable incoming (inbound) ICMP traffic
      - Re-enable ICMP traffic for the Network Security Group your Ubuntu VM is using
      - Stop the ping activity

- Observe SSH Traffic:

      - Back in Wireshark, filter for SSH traffic only (tcp.port == 22)
      - From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address)
      - Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark

- Observe DHCP Traffic:

      - Back in Wireshark, filter for DHCP traffic only (udp.port == 67/68)
      - From your Windows 10 VM, attempt to issue your VM a new IP address from the command line (ipconfig /renew)

- Observe DNS Traffic:

      - Back in Wireshark, filter for DNS traffic only (udp.port == 53)
      - From your Windows 10 VM within a command line, use nslookup to see what google.com and disney.com’s IP addresses are

- Observe RDP Traffic:

      - Back in Wireshark, filter for RDP traffic only (tcp.port == 3389)
      - Oserve the immediate non-stop spam of traffic

<h2>Actions and Observations</h2>

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
