---
description: with focus on the metasploitable 2 machine.
---

# Info Gathering with Metasploit

in the `msf >` console we can perform an nmap scan, `nmap -sT 192.168.81.132` this does a tcp 3-way handshake and discover open ports on the metasploitable 2 machine.

<figure><img src="../.gitbook/assets/Screenshot from 2023-03-22 14-15-07.png" alt=""><figcaption><p>nmap scan with metasploit</p></figcaption></figure>

`nmap -sS 192.168.81.132` to perform a stealth scan.

#### We can search for running ssh-version on the target;

`search ssh_version` allows you detect the ssh versions running on a target.

`show options` show list of options available for modification.

`set RHOST 192.168.81.132` to modify the RHOST value and `set THREADS 100` to set the threads. Then type `run` to run.

<figure><img src="../.gitbook/assets/Screenshot from 2023-03-22 14-42-34.png" alt=""><figcaption><p>ssh running on the metasploitable machine</p></figcaption></figure>

We can us the information to know the current open ssh version running on the victim machine then search for a vulnerability online.



n





