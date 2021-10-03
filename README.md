# EESTech Challenge - Cyber-Security

I participate on cyber security event organized by EESTech.

Idea of this event is to compete in one of three challenges. I participated in challenge provided by SmartCom team.

## Challenge

In SmartCom challenge we needed to hack into two machines and break root passwords.

We made following steps:
1. So at the beginning we need to find this machines in the local network and get their IPs. We do this with command `netdiscover`.
2. Next we need to find what vulnerabilities have this machines. For this step we used `nmap -sV [IP]` for scanning open ports.
3. 
    1. So in the previous step we found opened HTTP and FTP port in one machine. So we first tried to make so injection attack, but this not work. So then we decided to eavesdropping to FTP communication, where we intercepted file with passwords of one user. So that's how we came to the first assess to the machine.
    2. Next we figure out what operating system has. So we notice the version is very old. So we found some issue with this version and made privilege escalation exploit. With this attack we got admin control.
    3. In the next step we have assess to shadow file with password hashes. So we tried to crash this password with John The Reaper command (`john --wordlist`) and we made it.
    4. Next password we found in `.bash_history`, where was one of the root users changing password of user.
    5. We found last password hash, but we could not break last password. We used `hashcat` command, but after 12 hours we ended our challenge.

## Used tools

- KALI linux
- Wireshark
- Ettercap
- command line
