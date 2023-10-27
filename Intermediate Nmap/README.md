# Try Hack Me Writeup - Intermediate Nmap
- TryHackMe room: <https://tryhackme.com/room/intermediatenmap>
- OS: `Linux (Ubuntu)`

You've learned some great nmap skills! Now can you combine that with other skills with netcat and protocols, to log in to this machine and find the flag? This VM 10.10.206.67 is listening on a high port, and if you connect to it it may give you some information you can use to connect to a lower port commonly used for remote access!

The only task is to capture the flag:

## Enumeration ports and services 
nmap 10.10.206.67 -p- -A
-p-: To scan all ports
-A:  For aggressive scanning
![image](https://github.com/HDK99/TryHackMe_Writeups/assets/105449114/f978a6df-c012-4774-914c-4e1ab008e9d3)

We have ssh service on both port 22 and 2222, But we are intressted in the port 31337

## Check web server
10.10.206.67:31337
![image](https://github.com/HDK99/TryHackMe_Writeups/assets/105449114/8900effb-b78d-4462-ade9-a4cc59af6c2b)

## SSH-Login
ssh (found_user)@10.10.206.67
enter the password, And we are in
![image](https://github.com/HDK99/TryHackMe_Writeups/assets/105449114/4e2ebf89-8c5b-4452-8d0c-a2da27a56958)
to spawn a more interactive shell:
python3 -c "import pty; pty.spawn('/bin/bash')"
![image](https://github.com/HDK99/TryHackMe_Writeups/assets/105449114/db20b410-1f6d-4c77-bda7-7555cf5962a0)
## Get the flag
We have the permission to read the flag
