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

<img width="617" alt="image" src="https://github.com/user-attachments/assets/3f023efd-0d5b-4cd5-a05d-b42518b423a8" />

<img width="617" alt="image" src="https://github.com/user-attachments/assets/727f54fc-9203-4000-b7b1-9454dff05e24" />

<img width="617" alt="image" src="https://github.com/user-attachments/assets/e7265cda-c114-4b38-8cff-f2bdff8bf44a" />


</p>
<p>
Create a Windows 10 Virtual Machine (VM):
  
Create a Linux (Ubuntu) VM:

Use Remote Desktop to connect to your Windows 10 Virtual Machine:

</p>
<br />

<p>


<p>
<img width="779" alt="image" src="https://github.com/user-attachments/assets/9d606761-5f5a-4efd-8c1e-f3901d48ab2c" />

</p>
<p>
Use Remote Desktop to connect to your Windows 10 Virtual Machine. Within your Windows 10 Virtual Machine, Install Wireshark.
</p>
<br />

<p>

<img width="617" alt="image" src="https://github.com/user-attachments/assets/7e228edc-5bc6-4411-9f70-41cf52e963ca" />

<img width="617" alt="image" src="https://github.com/user-attachments/assets/e8b13f97-922b-409d-9e4a-488044d13d62" />
</p>
<p>
Open Wireshark and start packet capture. Within Wireshark, filter for ICMP traffic only
</p>
<br />
<br />

<p>
<img width="617" alt="image" src="https://github.com/user-attachments/assets/201c2b06-6e19-4fde-af6b-ac9fb5c8ac39" />
<img width="617" alt="image" src="https://github.com/user-attachments/assets/1a075a39-5d9a-43b7-aa66-d56b84bb59d8" />



Retrieve the private IP address of the Ubuntu VM (linux-vm) and attempt to ping it from within the Windows 10 VM

Observe ping requests and replies within WireShark

<p>
<img width="617" alt="image" src="https://github.com/user-attachments/assets/fb09f022-eda5-4e7c-b4a1-35499c2f52d7" />

<img width="617" alt="image" src="https://github.com/user-attachments/assets/b485d849-fefe-4152-a51d-645f8553d0d3" />

<img width="617" alt="image" src="https://github.com/user-attachments/assets/2d38ced3-ee06-495c-947c-978457cd67b6" />

<img width="617" alt="image" src="https://github.com/user-attachments/assets/5cf0ff2b-519a-4419-a5d9-a3be00134de4" />

<img width="617" alt="image" src="https://github.com/user-attachments/assets/731a2d8e-398c-4fcc-9296-ff140932d6e3" />


</p>
<p>
(Configuring a Firewall [Network Security Group])
Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM (ping ip address -t)
  
Open the Network Security Group your Ubuntu VM is using and disable incoming (inbound) ICMP traffic

Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity

Re-enable ICMP traffic for the Network Security Group your Ubuntu VM is

Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity (should start working)



</p>
<br />

<p>

<p>
<img width="617" alt="image" src="https://github.com/user-attachments/assets/f7a71e8b-b270-4d62-91f1-52eb3bff646b" />

<img width="617" alt="image" src="https://github.com/user-attachments/assets/f02118d9-7cd3-4f32-af69-7931e26b4a00" />

<img width="617" alt="image" src="https://github.com/user-attachments/assets/c9e5177e-1295-4dd4-b934-3e1696284824" />

<img width="617" alt="image" src="https://github.com/user-attachments/assets/66bf1515-99d3-4fe0-b68f-b67f004e706a" />

<img width="617" alt="image" src="https://github.com/user-attachments/assets/89097e21-a880-4e42-af61-362c31769094" />


</p>
<p>
Observe SSH Traffic
  
Log back into the windows-vm

Back in Wireshark, start a packet capture up

Filter for SSH traffic only

From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address)

Open PowerShell, and type: ssh labuser@<private IP address>

Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark

Exit the SSH connection by typing ‘exit’ and pressing [Enter]
</p>
<br />

<p>

<p>
<img width="617" alt="image" src="https://github.com/user-attachments/assets/6902677b-4e67-4417-abb0-8d2a4fdb8fc8" />

<img width="617" alt="image" src="https://github.com/user-attachments/assets/d3fe266c-56f4-404d-a2f4-f6300f91850b" />

<img width="617" alt="image" src="https://github.com/user-attachments/assets/5878af71-c533-4f07-9b47-f464b9f7f423" />


</p>
<p>
Observe DHCP Traffic
  

In Wireshark, filter for DHCP traffic only

From your Windows 10 VM, attempt to issue your VM a new IP address from the command line

Open PowerShell as admin and run: ipconfig /renew

Observe the DHCP traffic appearing in WireShark
