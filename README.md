# Metasploit-for-reconnaissance
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
![image](https://github.com/user-attachments/assets/08373461-3432-4497-8dd5-af9fd8012488)
Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:
```
systemctl start postgresql
```
```
msfdb init
```
Invoke msfconsole:

## OUTPUT:
![image](https://github.com/user-attachments/assets/78fae7eb-60ec-4a1f-a2e2-21b987c4c965)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![image](https://github.com/user-attachments/assets/0ec26caf-b256-458b-a3f4-b006e4f21140)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
## OUTPUT:
![image](https://github.com/user-attachments/assets/ef423142-a214-435d-bff5-ff2ffde003c0)
step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
## OUTPUT:
![image](https://github.com/user-attachments/assets/0dc3f1cf-4f95-4e2c-8899-f4fc3213a6d3)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
## OUTPUT:
![image](https://github.com/user-attachments/assets/ac10db74-3ad8-49a1-9577-892081796c8c)
Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
## OUTPUT:
![image](https://github.com/user-attachments/assets/67083f9e-264d-4061-909f-8347e45a359a)
The info command provides information regarding a module or platform,
![image](https://github.com/user-attachments/assets/154d7909-63f6-4ec5-bf91-4b5f3cfda26d)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:

```
systemctl start postgresql
```
```
msfbd init
```
## MYSQL ENUMERATION:

Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/user-attachments/assets/f3280cd4-94e1-402c-a23d-6101432c5e97)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![image](https://github.com/user-attachments/assets/cb6d6b12-7618-4fa2-8d07-de4d76bc30a6)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![image](https://github.com/user-attachments/assets/3f080265-c5db-4a61-be4e-a8b67a22beb8)
Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/user-attachments/assets/9614ae88-9f97-4c60-920d-82df94ef0f54)

scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/user-attachments/assets/eca92adf-4a41-4101-bd05-37ded7b8dcdc)
set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists:
```
set PASS_FILE /usr/share/wordlists/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS
```
Set BLANK_PASSWORDS to true in case there is no password set for the root account.
```
set BLANK_PASSWORDS true
```
![image](https://github.com/user-attachments/assets/845d97d1-98ec-46aa-82b5-421df6129632)



## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
