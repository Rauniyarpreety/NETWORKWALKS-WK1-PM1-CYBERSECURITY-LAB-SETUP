# 🔐 Cybersecurity Lab Environment Setup

**NetworkWalks | Week 1 | Project WK1-PM1**  
**Author:** Preety Rauniyar

A Windows 11-based virtual cybersecurity practice lab using Oracle VirtualBox, Kali Linux, and a private NAT Network. This repository documents the setup, tests, and evidence from my own environment.

> **Project status:** Lab setup completed.

## 📌 Project Overview

I use Windows 11 and Kali Linux in a dual-boot configuration. For this assignment, I additionally installed Kali Linux inside VirtualBox on Windows 11 to create a separate, controlled practice environment. The lab is designed for authorised learning, future network-security exercises, and repeatable configuration testing.

## 🎯 Objectives

- Install Oracle VirtualBox and Kali Linux as a guest virtual machine.
- Configure a NAT Network using `10.0.0.0/24`.
- Assign Kali Linux the required static address `10.0.0.2/24`.
- Confirm IP configuration, routing, DNS and internet access.
- Enable bidirectional clipboard and drag-and-drop.
- Share the host Windows folder with Kali.
- Record evidence and troubleshoot any real configuration issues.

## ⚙️ Lab Configuration

| Component | Configuration |
|---|---|
| Host operating system | Windows 11 |
| Hypervisor | Oracle VirtualBox (version: 7.2.22) |
| Guest operating system | Kali Linux (version: 2026.3) |
| Virtual network mode | NAT Network |
| Network prefix | `10.0.0.0/24` |
| Guest IP | `10.0.0.2/24` |
| Default gateway | `10.0.0.1` |
| DNS | `1.1.1.1`, `8.8.8.8` |
| Shared clipboard | Bidirectional |
| Drag and drop | Bidirectional |
| Shared folder | Windows Documents → Kali guest |

## 🪜 Setup Procedure

### 1. Install and configure VirtualBox

Installed VirtualBox on the Windows 11 host and prepared the guest VM. 

![VirtualBox Manager](screenshots/virtualbox.png)

### 2. Import the Kali Linux virtual machine

Imported the official Kali VM image into VirtualBox and started the guest. 

![Kali Linux Desktop](screenshots/kali-desktop.png)

### 3. Configure NAT Network

Created a NAT Network with the IPv4 prefix `10.0.0.0/24`, then attached Kali Linux virtual machine's network adapter to it. Verified the network configuration in VirtualBox.

![NAT Network](screenshots/nat-network.png)

### 4. Configure Kali IP and networking

Confirmed `10.0.0.2/24` on the Kali guest. Verification commands:

```bash
ip -br addr
```

![Kali IP Configuration](screenshots/ip-config.png)

### 5. Test internet and DNS

```bash
ping -c 4 google.com
```

![Internet Connectivity](screenshots/connectivity.png)

### 6. Configure guest integration and shared folder

Enabled bidirectional clipboard and drag-and-drop, then configured a permanent shared Document folder. Verified that the folder was accessible from Kali Linux. 

![VM Integration Settings](screenshots/vm-integration.png)

![Shared Folder](screenshots/shared-folder.png)


## 🛠️ Challenges and Troubleshooting

The cybersecurity lab setup was completed successfully without any major technical difficulties. VirtualBox and Kali Linux were installed and configured as required. The NAT Network, static IP address, internet connectivity, and shared-folder functionality were set up without significant issues.

## 💡 What I Learned

Using dual-boot Kali is different from running Kali inside a VM. I learned to configure a reproducible guest lab, distinguish **NAT** from **NAT Network**, use a consistent IPv4 address, and check networking using Linux terminal commands. I also practised sharing files between host and guest without confusing that integration with network connectivity.

## 🔐 Ethical Use

This lab is for education and testing systems I own or have explicit permission to assess. I will not publish passwords, personal files, VM disks, or private keys in this repository.

## 🔗 References

- [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- [Kali Linux virtual machines](https://www.kali.org/get-kali/#kali-virtual-machines)
- [7-Zip](https://www.7-zip.org/download.html)
- [NetworkWalks instructor's sample](https://github.com/waqaskarimccie/NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP)
