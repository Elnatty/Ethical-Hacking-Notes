---
description: mac address and how to modify/change them.
---

# Mac Address

1. disable the interface 1st.

```bash
ifconfig ether down
```

2. change the mac address.

```bash
ifconfig ether0 hw ether 00:11:22:33:44:55
```

3. enable interface.

```bash
ifconfig ether up
```

