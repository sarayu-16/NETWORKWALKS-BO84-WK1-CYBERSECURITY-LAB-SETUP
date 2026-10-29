# NETWORKWALKS-BO84-WK1-CYBERSECURITY-LAB-SETUP
Cybersecurity Lab- WEEK1 

A safe practice lab on my laptop. It uses VirtualBox and Kali Linux, a system with security tools. I can learn scanning and testing here without harming real systems.

My setup

Hypervisor: VirtualBox
Security OS: Kali Linux (2 GB RAM)
Network: NAT Network called NatNetwork (10.0.0.0/24)
Kali IP: 10.0.0.2
Gateway: 10.0.0.1
DNS: 8.8.8.8

Steps I did

Installed 7-Zip to extract the Kali file.
Installed VirtualBox.
Created the NAT Network.
Imported Kali and set its network adapter to NatNetwork.
Set a fixed IP address inside Kali.
Took a snapshot called “Clean Kali - Network Setup” as a backup.

How I checked it works

ip a shows my IP.
ping 10.0.0.1 tests the gateway.
ping 8.8.8.8 tests the internet.
ping google.com tests DNS.

Problems and fixes

No internet after setting a static IP: I ran sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0, then restarted the connection.
VM would not start (VT-x error): I turned on virtualization in the BIOS.

What I learned

NAT Network lets several VMs talk to each other and still reach the internet.
A static IP makes the lab easier to document.
A snapshot lets me go back to a working state.
Writing down problems and fixes is part of a good project.
Two things to fix in your original
Your document says Windows 10 and Kali 2026.2, but your screenshots show Windows 11 and Kali 2026.3. Make these match.
Your lab table says the DAD fix is a “workaround”, which is fine. You can also add the line ip route to your verification table, since that’s how you found the missing gateway.
