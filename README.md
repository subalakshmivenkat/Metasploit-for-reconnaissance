# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

## Step 2:
Investigate on the various categories of tools as follows:

## Step 3:
Open terminal and try execute some kali linux commands

## Step4: 
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.
scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## PROGRAM:
Find out the ip address of the attackers system

## OUTPUT:
![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/064e7fb3-b689-476f-b9ba-7b8faeae6049)


## Invoke msfconsole:
## OUTPUT:
![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/8d8e2ab0-f5aa-4c66-a446-a4dc0931b52f)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:
![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/4c908c6b-accd-418f-b820-803285ef6b20)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:
![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/5291588d-7b87-4226-bc25-da9c76cd4cfc)

## OUTPUT:
![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/1bf83db7-525f-44ee-ae0c-38c377b8dfbf)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:
![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/9f0123db-e442-4b0d-857f-89c6dafcfa46)
![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/a0b4da1d-f7d0-46a3-b88b-f8863c8dd031)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/fba211e6-7a41-4063-9158-ac12fe361c42)

The info command provides information regarding a module or platform

## OUTPUT:
![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/b9af032c-8336-4dfb-83b3-5d22017a97c8)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address> 

![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/093a7cbe-990c-45cc-969d-1ec78035fe5c)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/09f04394-fb43-4cee-b795-c779a5013d09)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/99a1ca62-7051-4a7f-b784-0f9ae6998a61)

Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/eb6512c6-c1de-42cf-b219-e2e332b7401b)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/e8f1a2c8-72c1-4d9e-991f-8b4cac227d29)


set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/subalakshmivenkat/Metasploit-for-reconnaissance/assets/119393477/49517f60-c5a1-4e0c-a98c-21b279fa9d6c)


## RESULT:
The Metasploit framework for reconnaissance is examined successfully## EXECUTION STEPS AND ITS OUTPUT:

