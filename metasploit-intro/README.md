---
description: metasploit basics
---

# Metasploit Intro

`msfconsole` launch the metasploit framework.

### Metasploit has 6 types of modules:

* **Exploits:** takes advantage of a system vulnerability to install a payload on the system.
* payloads
* Auxillary
* Post
* Encoders
* Nobs

### Basic cmds

`help` display help menu.

`use` allows you to load a module, eg - `use exploit/windows/browser/adobe_flash_avm2`

`show options` shows options we can modify/change concerning the loaded module.

`show payloads` displays compatible payloads for the loaded module.

`show targets` shows targets you can change/modify.

`show info` shows info about the exploits.

`search` allows you to search for certain exploits using some passed parameters such as; type, name, platform etc. example; `search type:exploit platform:windows flash`

`use 10` after searching you can easily select the number of your required module to select.

`use exploit/windows/browser/adobe_flash_avm2` after searching for the required module, you can use the `use` cmd to load it.

`show options` displays various options you can modify with respect to a loaded module.

`set SRVPORT 80` an example of changing/modifying various parameters in a loaded module.

`exploit` or `run` after modifying required parameters, you can use the `exploit` or `run` cmd to launch the exploit.

`back` takes you a step back just like the `cd ..`

`exit` to exit the msfconsole framework.





