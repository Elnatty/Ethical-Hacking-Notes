---
description: mac address and how to modify/change them.
---

# Mac Address

1. `ifconfig ether down` disable the interface 1st.
2. `ifconfig ether0 hw ether 00:11:22:33:44:55` change the mac address.
3. `ifconfig ether up` enable interface.

### or

1. disable interface.
2. `macchanger -r wlan0` to set a random mac addr. Use the --help to view more options.
3. enable interface.

