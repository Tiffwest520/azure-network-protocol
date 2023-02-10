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


<h2>Actions and Observations</h2>

<p>
<img src="https://imgur.com/zD7SQhw.png" height="80%" width="80%" />
</p>
<p>
In Azure portal create a resource group. From there create a Windows 10 VM and a Linux VM that share the same resource group, Vnet, and subnet. Observe the VM within the Network Watcher.
</p>
<br />

<p>
<img src="https://imgur.com/oKGiKiT.png" height="80%" width="80%" alt="linux Steps"/>
</p>
<p>
Observe ICMP Traffic: in VM-1 (Windows Virtual Machine) we'll install Wireshark. Then in wireshark filter for ICMP traffic only. Retrieve the private IP address of the Ubuntu VM. Observe the ping requests and replies within WireShark
</p>
<br />

<p>
<img src="https://imgur.com/IUjAMrD.png" height="80%" width="80%" />
</p>
<p>
In Wireshark, filter for SSH traffic only. From VM-1, SSH into your Ubunto VM private IP. Then type pwd into the SSH connection to observe the traffic in wireshark.
</p>
<br />

<p>
<img src="https://imgur.com/huXbwu4.png" height="80%" width="80%" />
</p>
<p>
In Wireshark, filter for DHCP traffic only. From the Windows 10 VM, use ipconfig /renew to attempt to issue the VM a new IP from the command line.
</p>
<br />

<p>
<img src="https://imgur.com/Zxr7Nmq.png" height="80%" width="80%" />
</p>
<p>
In Wireshark, filter for DNS traffic only. From the Windows 10 VM, within the command line, use nsloolup to see google.com IP address is.

</p>
<br />

