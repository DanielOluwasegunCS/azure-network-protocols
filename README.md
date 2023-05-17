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
<img src="https://imgur.com/5bDZuHZ.png" height="300%" width="300%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this image, we witness the process of creating a virtual machine (VM) within the expansive Microsoft Azure cloud computing platform. This is within the Azure portal, where I am configuring the necessary settings to create a Windows 10 VM.
</p>
<br />

<p>
<img src="https://imgur.com/v46vz2e.png" height="400%" width="400%" alt="Disk Sanitization Steps"/>
</p>
<p>
This image encapsulates another process of creating a VM within Microsoft Azure, but this time I am creating a linux VM. I am always reminded of the remarkable opportunities provided by cloud computing.
</p>
<br />

<p>
<img src="https://i.imgur.com/4lnJKuv.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
This image displays the ping requests and replies within Wireshark while pinging a public website and the Linux VM from the Windows 10 VM. Wireshark allows you to analyze the network traffic and gain insights into the communication between your VM and the destination website/other VM.
</p>
<br />

<p>
<img src="https://i.imgur.com/oBzjCjg.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this image, we delve into the realm of network analysis as we see the process of observing Secure Shell (SSH) traffic within Wireshark, from a Windows 10 VM. I am still within the Wireshark interface, I am observing the intricacies of network packets. The screen presents an array of captured network packets, showing the SSH communication.
</p>
<br />

<p>
<img src="https://i.imgur.com/oBzjCjg.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this image, we explore the domain of network analysis by observing the process of monitoring Dynamic Host Configuration Protocol (DHCP) activity within Wireshark, using a Windows 10 virtual machine. I used the command line "ipconfig /renew" in order to observe the DHCP traffic/network packets. 
</p>
<br />

<p>
<img src="https://i.imgur.com/lCPcYHl.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this image, we venture into the domain of network analysis by observing the process of monitoring Domain Name System (DNS) activity within Wireshark, using a Windows 10 virtual machine. By using the command "nslookup (website domain name)" I am able to not only observe DNS traffic in Wireshark, I can also see the IP addresses of those websites, which I find so fascinating.
</p>
<br />

<p>
<img src="https://i.imgur.com/DMZTMgJ.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this image, we inspect the domain of network analysis by observing the process of monitoring Remote Desktop Protocol (RDP) activity within Wireshark, using a Windows 10 virtual machine. Here, I didn't have to do much of anything to observe the RDP traffic because RDP is constantly showing me a live stream from one computer to another, therfore traffic is always being transmitted.
</p>
<br />
