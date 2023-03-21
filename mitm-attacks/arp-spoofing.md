---
description: mapping ip address to mac addresses.
---

# ARP SPOOFING

There are various tools used to perform this attacks which includes: **Arpspoof or Driftnet.**

### arpspoof attack:

```bash
# "-i" denotes the interface to perform the attack, "-t" signifies the target, so we specify the target and the gateway to fool the target/client that we are the AP/gateway.
arpspoof -i eth0 -t 192.168.81.129 192.168.81.2

# "-i" denotes the interface to perform the attack, "-t" signifies the target, so we specify the target and the gateway to fool the AP/Gateway that we are the client.
arpspoof -i eth0 -t 192.168.81.2 192.168.81.129
```

The image below shows us that the attack worked, now the victim/client thinks its AP/router-gw mac is 00:0c:29:3e:1d:5c (192.168.81.128) which is our kali pc instead of 00-50-56-ef-b5-04 (192.168.81.2) which is the correct router-GW mac. ie; we have successfully fooled the client to thinking our kali pc is the real gateway now.

<figure><img src="../.gitbook/assets/Screenshot from 2023-03-21 22-59-22.png" alt=""><figcaption><p>arp poison on the victim windows machine.</p></figcaption></figure>

At this juncture, our kali pc cant do anything with the traffic by default, so we have to enable port forwarding on our kali pc so it can allow packets flow through it just like a router would.

`echo 1 > /proc/sys/net/ipv4/ip_forward` cmd to enable port forwarding in kali.

After enabling Port-Forwarding on the Kali PC, all packets coming from the victim pc passes through the kali, then the kali forwards all request packets to the router/AP, then the get the response back and forward it to the victim, making our kali in control of the whole session, we can inject code into the victim browser, steal usernames, passwords, replace downloaded files with Trojans, etc.







