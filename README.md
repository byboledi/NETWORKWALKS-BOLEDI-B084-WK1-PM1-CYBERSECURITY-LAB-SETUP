# Cybersecurity Lab Environment Setup (Task WK1-PM1)

Building an isolated virtual lab for penetration testing and ethical hacking practice using VirtualBox and Kali Linux.

## Project Overview
The purpose of this project is to establish a secure, controlled, and isolated sandbox environment on a local host machine. This infrastructure allows for safe network scanning, traffic analysis, and exploit testing without risking production data or violating external network boundaries.

## Lab Architecture & Parameters
- **Virtualization Base:** VirtualBox (Latest Stable Build)
- **Attacking OS Platform:** Kali Linux AMD64 Pre-built Appliance
- **Network Architecture Platform:** Custom VirtualBox NATNetwork
- **Target Subnet IP Range:** 10.0.0.0/24
- **Hardcoded Guest Identity:** 10.0.0.2 / 24
- **Default Gateway Link:** 10.0.0.1
- **Primary DNS Resolution:** 8.8.8.8
- **Promiscuous Interface Mode:** Allow All

## Implementation Phases

### Phase 1: Network & Virtual Layer Infrastructure
1. Created a global `NatNetwork` profile inside VirtualBox Network Tools with the manual prefix `10.0.0.0/24` and enabled internal DHCP allocation.
2. Unpacked the Kali Linux `.7z` container archive using 7-Zip File Manager tools.
3. Registered and initialized the `.vbox` target file straight into the VirtualBox Manager pane via command prompt scripting.
4. Adjusted hardware properties to configure a bidirectional shared clipboard and drag-and-drop mechanism.
5. Integrated the host machine's `/downloads` folder path into the storage manager to auto-mount a permanent shared directory folder (`sf_downloads`).

### Phase 2: Guest Network Hardening & Connectivity Verification
1. Launched the Kali Linux virtual appliance framework.
2. Modified the `Wired connection 1` adapter properties from DHCP configuration to explicit Manual routing.
3. Assigned the static IP profile: `10.0.0.2`, netmask `24`, and gateway `10.0.0.1`.
4. Successfully reloaded interface modules using the NetworkManager control script framework.
5. Executed connectivity evaluation tests via terminal to verify external internet accessibility.

## Verification Proof of Work
Below is the terminal output capture displaying stable packet transmissions to Google's public DNS servers alongside active validation metrics:

![Kali Linux Internet Ping Verification](kali_ping_success.png)
