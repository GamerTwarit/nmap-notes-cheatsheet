stealth scan is done by -sS

UDP scan for list of open ports by -sU

-O for checking operating system

checking version of services -sV

for more information ie verbosity -V and to increase the verbosity its -vv

now for saving the nmap scan , (all files -oA) (normal format -oN) (greppable -oG) 

aggressive scan does almost everything, like its aggresive -A

in nmap time is a thing agressive scans or low timed scans are noisy and people can get caught -T0 (paranoid), -T1 (polite), -T2 (normal), -T3 (aggressive), -T4 (fast), or -T5 (brutal)

if we want to scan particular ports we can use -p <port number>, we can add more ports with "-"

to scan all the ports we shall use -p-

to use our own script we shall use --script

to activate all vurn scripts we shall use --script=vuln

the types of NSE. nmap scripting engine:-
    safe:- Won't affect the target
    intrusive:- Not safe: likely to affect the target
    vuln:- Scan for vulnerabilities
    exploit:- Attempt to exploit a vulnerability
    auth:- Attempt to bypass authentication for running services (e.g. Log into an FTP server anonymously)
    brute:- Attempt to bruteforce credentials for running services
    discovery:- Attempt to query running services for further information about the network (e.g. query an SNMP server).
for more scripts https://nmap.org/book/nse-usage.html


NSE scripts are written in LUA, yes even roblox games are made on that script 

its a bad idea to use intrusive script in a productive environment

To run a specific script, we would use --script=<script-name> , e.g. --script=http-fileupload-exploiter.
Multiple scripts can be run simultaneously in this fashion by separating them by a comma. For example: --script=smb-enum-users,smb-enum-shares.

to find some scripts we use use it like 

here cd should be /usr/share/nmap/scripts/
grep "smb" /usr/share/nmap/scripts/script.db


while scanning
SYN request is sent
if a server is closed then RST flag is returnes
SYN scan cant be run with
