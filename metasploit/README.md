---
description: metasploit basics
---

# Metasploit

For more info on kali metasploit framework: [https://www.kali.org/docs/tools/starting-metasploit-framework-in-kali/](https://www.kali.org/docs/tools/starting-metasploit-framework-in-kali/)

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



### Location of the Metasploit Modules;

metasploit files are located at the: `cd usr/share/metasploit-framework/modules`

1. `/modules/exploits` contains exploits available for various OS's (linux, windows, apple, android, etc.
2. `/modules/payloads` payload are files left on the exploited system. they give the attacker access or control over the system.

* `/payloads/singles` these are small pieces of codes that are designed to take one single actions / attacks.
* `/payloads/stagers` are used for creating a  communication btw the attacker and target, which can be further used to deliver another payload.
* `/payload/stages` are very very large payloads that can give the attacker a very very good control over the target eg; meterpreter instances or vnc connections.

3. `/modules/auxillary` gives the attacker unique types of attacks such as; DOS, fuzz, vuln scanner functionalities etc. They allow for scanning a target system for vulnerabilities and to perform DOS attacks.
4. `/modules/encoders` are used to re-encode payloads and exploits, evasion techniques / getting past antivirus systems
5. `/modules/nops` (no operation) this causes the cpu to do nothing for an entire clock circle, it allows the attacker run a specific code/file after exploiting the buffer overflow.
6. `/modules/post` for post exploitation attacks.



### When you successfully gain access into say a windows.

The `meterpreter >` interactive shellis loaded.

You can use cmds like: `getuid` to get server info.

You can also use the `shell` cmd to launch the default windows cmd prompt.

You can minimise your current session with `ctr+z`

Then type `sessions` to view minimised sessions.

### How to upgrade shell to meterpreter.

`search shell_to` search for the shell to meterpreter exploit in msfconsole.

`show options` - show the options available for modification.

`set SESSION 1` - the `1` denotes the initial default meterpreter session you were in before. So you have to set the SESSION value to its number, in this case 1.

> So thats how to upgrade a cmd shell to a meterpreter shell.
>
> `sessions 1` switches you back into your upgraded shell now.
>
> ### CMDS you can you to verify:
>
> * `sysinfo` - view sys info details.
> * `shell` - takes you to the default windows cmd prompt command line.
> * `exit` - go back to the meterpreter session.

### Search for files in meterpreter sessions:

`search -f flags.txt` - searches the system for the file flags.txt

### Some meterpreter cmds

`sessions -K` - kill all sessions.

`pgrep service_name` - this searchs for any running process/service on the target PC and returns the PID.



