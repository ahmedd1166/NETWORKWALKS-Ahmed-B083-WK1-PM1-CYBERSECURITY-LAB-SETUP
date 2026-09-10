# NETWORKWALKS-Ahmed-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP
An Isolated virtual Kali Linux lab for cybersecurity testing and penetration testing practice.
Cybersecurity Lab Setup & Network Configuration
Overview
This repository documents the network configuration and laboratory setup performed during my internship project. The primary objective of this task was to configure static IP addressing and manage network connections on a Kali Linux virtual machine using both graphical interface tools and the Network Manager Command Line Interface (nmcli).

Lab Environment
Host Platform: Oracle VM VirtualBox

Operating System: Kali Linux (2026.2)

Networking Mode: Bridged / Host-Only Adapter (Wired Connection 1)

Step 1: Static IP Address Configuration
To establish a controlled network environment for cybersecurity testing and lab exercises, a static IPv4 configuration was assigned to the primary wired network interface (Wired connection 1).

Configuration Parameters:
Method: Manual

IP Address: 10.0.0.2

Netmask / Prefix: 24 (255.255.255.0)

Gateway: 10.0.0.1

DNS Servers: 8.8.8.8

Step 2: Applying Network Changes via Terminal (nmcli)
After updating the network profile, command-line utility nmcli was used to apply the configuration changes, disable duplicate address detection (DAD) timeout, and restart the network interface to ensure persistence and connectivity.

Commands Executed:
Bash
# Modify DAD timeout for the connection profile
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

# Deactivate the network connection
sudo nmcli connection down "Wired connection 1"

# Activate the network connection with new static parameters
sudo nmcli connection up "Wired connection 1"
Verification:
The terminal output confirmed successful deactivation and activation of Wired connection 1 via DBus/NetworkManager.

Step 3: Connectivity & Browser Testing
Following the network restart, connectivity was verified by launching the web browser (Mozilla Firefox) within Kali Linux to confirm local network routing and internet gateway access.

Internship Learnings & Outcomes
Gained practical experience in configuring static networking parameters on Linux-based security distributions.

Mastered command-line network management using nmcli to troubleshoot and restart network interfaces without relying solely on desktop GUIs.

Established a stable foundation for subsequent penetration testing and lab simulation exercises.
