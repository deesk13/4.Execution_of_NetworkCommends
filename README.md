# 4.Execution_of_NetworkCommands
# NAME: DEVA DHARSHINI I

# REGISTER NO: 212223240026
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## PROGRAM
CLIENT
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
SERVER
```import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
TRACER
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```

## Output
CLIENT
![Screenshot 2024-05-07 091220](https://github.com/deesk13/4.Execution_of_NetworkCommends/assets/150927063/188c834d-7c1d-42bb-84c1-4e428c08f8e2)
SERVER
![Screenshot 2024-05-07 091250](https://github.com/deesk13/4.Execution_of_NetworkCommends/assets/150927063/a54b1acc-f11d-4b08-8c60-1628fa0818e6)
TRACER
![Screenshot 2024-05-07 091204](https://github.com/deesk13/4.Execution_of_NetworkCommends/assets/150927063/db8de54d-fbae-4fcc-95a7-78bfcb6a181d)

## Result
Thus Execution of Network commands Performed 
