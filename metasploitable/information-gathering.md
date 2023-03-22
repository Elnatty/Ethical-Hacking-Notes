---
description: info gathering on metasploitable.
---

# Information Gathering

### Using Zenmap to scan the machine:

`nmap -T4 -A -v 192.168.81.132` cmd on zenmap to scan all open ports.

<figure><img src="../.gitbook/assets/Screenshot from 2023-03-22 02-01-00 (1).png" alt=""><figcaption><p><code>zenmap scan</code></p></figcaption></figure>

### Exploiting port 21

for this we download the rsh-client on kali `apt install rsh-client` and use the `rlogin -l root 192.168.81.132` to login as root, `-l` denotes user ie; root.



You can google all the open ports and their exploits.



