---
description: >-
  a utility to put wireless network card adapters into managed, monitor or
  promiscious mode.
---

# Airmon-ng

`airmon-ng start wlan0` put wireless adapter card into monitor mode.

`airmon-ng stop wlan0` put wireless adapter card into managed mode.

### or

`iwconfig wlan0 mode Monitor` 2nd method of enabling monitor mode.

### or

`ifconfig wlan0 down` 3rd method of enabling monitor mode.

`airmon-ng check kill` kill all running process that will interfere with the process.

`airmon-ng start wlan0` switch to monitor mode.
