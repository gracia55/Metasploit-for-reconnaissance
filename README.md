# Metasploit-for-reconnaissance
NAME:GRACIA RAVI(212222040047)

# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find out the ip address of the attackers system

## OUTPUT:
![Screenshot 2024-10-28 152645](https://github.com/user-attachments/assets/2b32e6dd-495e-4f93-8130-c95405e95d38)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:

systemctl start postgresql

msfdb init

Invoke msfconsole:


## OUTPUT:
![Screenshot 2024-10-28 152703](https://github.com/user-attachments/assets/ebb99311-a7c3-4e50-a095-9b9761b8f76a)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![378183409-a317ac2a-bd89-4ced-894a-6986f4ae9f40](https://github.com/user-attachments/assets/9a0af61f-0810-4c56-8f8e-bab017e31955)
Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:
![378183974-cd992424-98b6-4c49-a8dc-5670b7e28c79](https://github.com/user-attachments/assets/34dfb9e2-944e-4361-b21f-937ef240d6bd)

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:
![374869604-510b37f3-684b-4026-82b4-45453f481f97](https://github.com/user-attachments/assets/4bd95ef2-cd19-4f93-ac4b-ecef1228e686)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:
![374869514-a0181c59-c096-4faa-80e6-1f331389314d](https://github.com/user-attachments/assets/a975e3f4-5b0c-4341-a817-c39a2a7eff0d)
Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
## OUTPUT:
![378185827-aaccb17a-a90e-469f-bbfe-5e6c4e4d2ece](https://github.com/user-attachments/assets/52326ab4-f28d-4e88-9ab3-e7c4e824471d)

The info command provides information regarding a module or platform,
![374869324-d99e2691-cfba-4be1-accd-cfcc4056a2cf](https://github.com/user-attachments/assets/08835a55-9401-4025-9e47-23e1954ddb54)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:

    systemctl start postgresql

    msfdb init

## MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![374869284-817e5096-8eb6-4cd3-9a50-7f89ee90f679](https://github.com/user-attachments/assets/cead89e2-9d4d-4139-aa25-d655d8dae2c8)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![374869188-eb9e3449-81ba-4cc8-b887-38cf737cafa3](https://github.com/user-attachments/assets/f61076ed-ec9c-4955-b670-cbaf3ee8e762)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![374869130-cbafb8e9-92b6-4d99-8f6c-ee556bf90ac8](https://github.com/user-attachments/assets/60e3bb19-e366-434f-b7eb-0adafb73c2ae)
Use the set rhosts command to set the parameter and run the module, as follows: 
![374869078-3855f7bf-e596-4158-a8e2-ddc757e1a122](https://github.com/user-attachments/assets/e0213665-cf63-48d9-963b-8c2c08c44712)
After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![374869044-f61c9740-5ab5-4046-90d7-40cf9c96f39b](https://github.com/user-attachments/assets/d056142e-497c-404c-8a0f-893f67276c4d)
set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists:

    set PASS_FILE /usr/share/wordlists/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS

Set BLANK_PASSWORDS to true in case there is no password set for the root account.

    set BLANK_PASSWORDS true

![374869005-38c66082-ef48-4a0c-a8cd-2d9dd0e4e188](https://github.com/user-attachments/assets/2843af46-b4fc-4960-93a4-c73df9a5dfc2)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
