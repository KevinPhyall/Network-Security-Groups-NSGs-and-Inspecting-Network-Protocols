# Network-Security-Groups-NSGs-and-Inspecting-Network-Protocols

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

- Step 1 Install Microsoft Remote Desktop
- Step 2 Install Wireshark
- Step 3 Ping and observe requests and replies within WireShark
- Step 4 Ping a public website

<h2>Actions and Observations</h2>

<p>
<img width="779" alt="image" src="https://github.com/user-attachments/assets/9d606761-5f5a-4efd-8c1e-f3901d48ab2c" />

</p>
<p>
Use Remote Desktop to connect to your Windows 10 Virtual Machine. Within your Windows 10 Virtual Machine, Install Wireshark.
</p>
<br />

<p>


<img width="779" alt="image" src="https://github.com/user-attachments/assets/5fb7bb9d-d509-4172-9d30-d861da0c87d0" />

</p>
<p>
9. Open Wireshark and start packet capture
10. Within Wireshark, filter for ICMP traffic only
</p>
<br />

<p>
<img width="693" alt="image" src="https://github.com/user-attachments/assets/eb1e7be9-d704-43af-84cd-8c554c792323" />

</p>
<p>
Within Wireshark, filter for ICMP traffic only.
</p>
<br />

<p>
<img width="617" alt="image" src="https://github.com/user-attachments/assets/201c2b06-6e19-4fde-af6b-ac9fb5c8ac39" />
<img width="617" alt="image" src="https://github.com/user-attachments/assets/1a075a39-5d9a-43b7-aa66-d56b84bb59d8" />

</p>
<p>
Retrieve the private IP address of the Ubuntu VM (linux-vm) and attempt to ping it from within the Windows 10 VM
Observe ping requests and replies within WireShark.

