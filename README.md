# B083-WK1-PM1-CYBERSECURITY-LAB-SETUP
**Building a virtual lab in VirtualBox for learning penetration testing and ethical hacking.**
<img src="Kali Linux desktop.png" alt="Kali Linux desktop">

# Project Overview
This project sets up a virtual cybersecurity lab using VirtualBox and Kali Linux. 
It provides a safe environment to learn and practice penetration testing, network scanning, reconnaissance, and vulnerability testing. 
A private network is used so more virtual machines can be added as testing targets.

# Objectives
The project objectives are to:

Install and set up VirtualBox.
Install Kali Linux as a virtual machine.
Create a private NAT Network for the lab.
Set up network access for Kali Linux.
Give the Kali VM a constant IP address.
Test the network connection and DNS.
Create a clean snapshot for recovery.
Document the setup steps.

# Project Purpose
The purpose of this lab is to provide a safe and controlled environment for learning cybersecurity and practicing authorized security testing.

The lab can be used for activities such as:

Network reconnaissance
Port scanning
Checking for vulnerabilities
Packet analysis
Web security testing
Practicing exploitation
Testing different security tools

**Important**: This lab should only be used on systems that you own or have permission to test. Do not use these tools to attack or test unauthorized systems.

# Lab configuration

 |Component | Config|
 |----------|-------|
 |Host OS | Windows 11 |
 |Host RAM | 32 GB |
 |Processor | Intel Core i5 |
 |Hypervisor | VirtualBox 7.2 |
 Security OS | Kali Linux 2026.2 |
 Kali RAM | 2048 MB |
 Virtual Network | NAT Network |
 Network Address | 10.0.0.0/24 |
 Kali IP Address | 10.0.0.2/24 |
 Default Gateway | 10.0.0.1 |
 DNS Server | 10.0.0.1, 8.8.8.8 |
 Future VM Range | 10.0.0.3 – 10.0.0.99 |

# Lab Setup Steps
**1. Install 7-Zip**
7-Zip was installed to extract the Kali Linux virtual-machine package.

**2. Install VirtualBox**
VirtualBox was installed as the hypervisor.

**3. Create the NAT Network**
A dedicated NAT Network (10.x.x.x) was created in VirtualBox.

**Configuration**:
<img src="NAT Network creation.png" alt="NAT Network creation">

Network Name: NatNetwork 
IPv4 Prefix: 10.0.0.0/24 
DHCP: Enabled 
IPv6: Disabled

**4. Import Kali Linux**
The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM network adapter was configured as follows:

<img src="Assigning created network to VM.png" alt="Assigning created network to VM">

**Adapter 1**
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop

**The VM System:**
Allocated: 
CPU - 2 Cores
RAM - 2048 MB

Configured a shared folder to allow file transfer between the host OS and the VM.

 **5. Configure the Kali Linux Network**
Kali VM was configured with a static ip address as follows:

<img src="VN network setup.png" alt="VN network setup">

IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 10.0.0.1, 8.8.8.8

 **6. Create a Clean VM Snapshot**
After completing the initial configuration, a VirtualBox snapshot was created.
This will help in restoring the VM to it previously working state, should an exercise or changes damage it.

# Problems Encountered & Solutions
**Problem**
When I initially created the VM, configured it with the given IP and used the gateway as a DNS, everything worked and I could search the internet, so I shutdown the VM and took a snapshot.
When I booted my VM again the following day, network was not working but I could ping Googles IP address.
I ran this command **sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0** but it still could not fix the issue.

**Solution**
I went back to network settings and configured the DNS for the ipv4 address to use Googles IP address as a secondary DNS. 
Switched network off and on then ping Googles IP again successfully.
I then went to the browser and performed a search on Google. I also opened YouTube and searched for videos successfully.
I shutdown the VM and took a snapshot.

<img src="Successful internet connection.png" alt="Successful internet connection">

# What I Learned
Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.

**1. Virtual Machine**
I learned how to setup a virtual machine on a VirtualBox. I learned that you can mount/create many virtual machines of different types of OS and can run more than one at the same time. You can link them communicate with each other via network.

**2. NAT Network**
I learned that a NAT Network allows multiple virtual machines to communicate with each other on the same virtual network while providing internet connectivity through NAT. I configured a static IP address for the machine following the IP assignment protocol, pinged Google and tested network connectivity. 

**3. VM Snapshots**
I learned that it is a good idea to take a clean snapshot before trying risky or new activities. This allows me to easily restore the VM to its previous working state if something goes wrong.

**4. Documentation**
I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

# Security & Ethical Use
This laboratory is intended strictly for education purposes only.

# Tools & Resources
7-Zip: https://7-zip.org/download.html

VirtualBox: https://virtualbox.org/wiki/Downloads

Kali Linux: https://kali.org/get-kali

# Author
**Sikhanyiso B. Sibisi**
Cybersecurity Intern - B083

LinkedIn: https://za.linkedin.com/in/sikhanyiso-b-s-a28a0b13a

# Project Information
GitHub | Repository|
-------|-----------|
Program Name| Cybersecurity at Networkwalks |
Project | Cybersecurity & Pentesting Lab Setup | 
Week | 01 | 


