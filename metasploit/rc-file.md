---
description: Metasploit rc file
---

# RC file

An RC file stands for Resource Script, which can be used to automate various aspects of metsploit through the msfconsole.

```bash
#create a .rc file
nano handler.rc

use multi/handler
set payload windows......
set LHOSTS or RHOSTS
set LPORT or RPORT
run

#to use the file
>$ msfconsole -r handler.rc
```

