 Malware Detection & Endpoint Security (Kali Linux)

Overview
This session focused on understanding how malware behaves, how to detect signs of infection on Linux systems (like Kali), and how to secure endpoints using manual investigation techniques.

What I Did

Learned how malware like worms, trojans, ransomware, and keyloggers work.
Identified common malware hiding spots in Linux (like /tmp, /dev/shm, /var/tmp).
Used commands to detect suspicious processes, network activity, and cron job persistence.
Practiced manually investigating and removing malware processes.
Documented a safe response plan to handle such threats.

Key Linux Commands Used

Check for Suspicious Processes
->ps aux | grep -E '/tmp|/var/tmp|/dev/shm'
Lists running processes located in folders often abused by malware.
Check Open Network Connections

->sudo netstat -tulpn
Reveals which processes are listening or making outbound connections.

Investigate Suspicious File
-file /path/to/file
-strings /path/to/file | less
Shows the file type and any readable content (e.g. URLs, IPs, commands).

Kill and Remove Malicious Process/File
->sudo kill -9 [PID]
->s-udo rm -f /path/to/malware

Persistence Check (Cron Jobs)
List current user's cron jobs
->crontab -l
Check system-wide cron jobs
->sudo cat /etc/crontab
->List all scheduled cron files/scripts 
->ls -la /etc/cron.* /var/spool/cron/crontabs
Look for anything pointing to /tmp, hidden scripts, or unexpected entries.

Basic Patching Steps
Kill and delete any suspicious process/file.

Check for persistence (cron jobs, services).

Update the system:

->sudo apt update && sudo apt upgrade -y
Secure /tmp and /var/tmp so nothing can run from there:

->sudo mount -o remount,noexec /tmp
What I Learned

How to recognize unusual process behavior using ps, netstat, and strings.
Where malware often hides and how it restarts itself using cron.
That endpoint security is more than antivirus — it's about visibility and control.
Manual tools (like grep, htop, systemctl) are powerful when used right.

Final Tip
If you see weird files running from /tmp, using lots of CPU, or talking to unknown IPs — assume it's malware until proven safe.