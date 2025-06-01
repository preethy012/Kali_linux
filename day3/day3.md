#DAY 3
OS Security, Nmap Scanning & Hardening Project


The lab Setup:
Attacker VM: Kali Linux
Target VM: Metasploitable2
Connected via NAT

Nmap Scanning (from Kali)
The commands I used to scan the <target_ip>:

nmap -sS -T4 -p 1-1000 <target_ip>             
nmap -sV -O <target_ip>                        
nmap --script vuln <target_ip>               
nmap -A -oN scan_report.txt <target_ip>       

UFW Firewall Configuration

Install and use UFW:

sudo apt install ufw
sudo ufw allow 22
sudo ufw deny 21
sudo ufw deny 80
sudo ufw enable
sudo ufw status

Mini Project: Linux Hardening

Check and block unused ports

sudo netstat -tulpn
sudo ufw deny [port]
Enforce strong password policy

sudo apt install libpam-pwquality
sudo nano /etc/pam.d/common-password
Add/edit this line:
password requisite pam_pwquality.so retry=3 minlen=12 

Disable root SSH login

sudo nano /etc/ssh/sshd_config
# Set: PermitRootLogin no
sudo systemctl restart sshd

Update the system

sudo apt update && sudo apt upgrade -y
Create Report File
Create day4.md and document:

Ports I blocked
UFW rules
Password policy applied
SSH setting changes
Update date
Why root login was disabled


