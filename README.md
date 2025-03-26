# Splunk & Active Directory Lab
<br>

## Objective

The Splunk & Active Directory project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

### Skills Learned

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used

- Active Directory Domain Services (ADDC) – Server that runs Microsoft Active Directory and manages authentication, authorization, and directory services in a Windows domain.

- Active Directory Users and Computers (ADUC) – Microsoft Management Console (MMC) snap-in used for managing Active Directory (AD) objects.

- Atomic Red Team - A library of small, portable tests, mapped to the MITRE ATT&CK framework, that security teams can use to quickly and reproducibly test their environments for detection and response capabilities

- Hydra – Fast and powerful password-cracking tool used for brute-force attacks against various network protocols and authentication services.

- RDP – Protocol that allows users to remotely access and control another computer over a network.

- Splunk – Security Information and Event Management (SIEM) system for log ingestion and analysis.

- Splunk Universal Forwarder – A lightweight agent that collects and forwards log data from various sources to a Splunk indexer for analysis.

- Sysmon – Windows system service and driver that logs detailed system activity, including process creation, network connections, and file modifications.

- VirtualBox – Open-source virtualization software that allows users to run multiple operating systems on a single machine.

<br>

## Steps
<br> 
<div>
Create Network Diagram (Include IP Addresses / Names for Machines)
  <br>
   <img src="https://i.imgur.com/X9VzTIN.png" />

**Ref 1: Network Diagram**

1) Install VMs listed in Network Diagram using VirtualBox
2) Download Splunk and install on Ubuntu Server
3) Test that the Splunk Server is working by accesing it via the Windows 10 VM. Use a Web Browser and the server's static IP Address with port 8000. If it was correctly setup, it will be reachable. 
4) Install the Splunk Forwarder on both the ADDC Server and Windows 10 VM.
5) Configure the inputs.conf file for the local folder in the Splunk Universal Forwarder. This will capture specific values that will be sent to the Splunk Server.
6) Install Sysmon on both the ADDC Server and Windows 10 VM. This will log detailed system activity like process creation, network connections and file modifications.
7) Create a Splunk index that corresponds with the index created in the inputs.conf file for ADDC and Windows 10 VMs.
8) Install ADDC, create domain controller, setup group, OUs, and users in ADUC.
9) Connect Windows 10 VM to Domain.
10) Configure Static IP for Kali Linux VM.
11) Add ADUC user's password(s) to wordlist.txt in Kali Linux Box.
12) Setup RDP on Windows 10 Machine and add ADUC users to Remote Desktop Users.
13) Use Kali Linux VM and Hydra to launch a brute force attack against Windows 10 VM using RDP protocol.
14) View Telemetry in Splunk and look for the 4625 event ID that indicates the failed login attempts from the brute force attack.
15) View Telemtry in Splunk and look for the 4624 event ID that indicates the successful login from the brute force attack.
16) Install Atomic Red Team on Windows 10 VM using Powershell.
17) Run MITRE ATT&CK Technique ID tests to replicate attacks on Windows 10 VM.
18) Make sure the technique ID tests are being logged in Splunk.
19) If the tests aren't being logged it would indicate a gap in your system security.
  
</div>

## Video

[![Watch the video](https://img.youtube.com/vi/G3BbQWCXSFU/0.jpg)](https://www.youtube.com/watch?v=G3BbQWCXSFU)
<br>
[![Watch the video](https://img.youtube.com/vi/rfvxSoyqAwo/0.jpg)](https://www.youtube.com/watch?v=rfvxSoyqAwo)
