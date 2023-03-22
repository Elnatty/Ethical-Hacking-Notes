---
description: a huge security scanner.
---

# Info Gathering with Nmap

Scans Ip's, open ports, running services, OS, connected clients, etc.

### Zenmap&#x20;

This is a gui representation of nmap.

`nmap -sn 192.168.81.0/24` scans network for pingable devices.

`nmap -T4 -F 192.168.81.1/24` where `-T4` is for quick scan, `-F` is to scan fewer most common ports.

