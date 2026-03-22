
## AIM :
Use of Network commands in Real Time environment
## Software :
Command Prompt And Network Protocol Analyzer
## Procedure:
To do this EXPERIMENT- follows these steps:

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

## Algorithm

Algorithm: Server Ping Program

1.Start the program.
2.Import socket and pythonping modules.
3.Create a socket.
4.Bind the socket to localhost and port 8000.
5.Listen for client connections.
6.Accept the client connection.
7.Receive hostname from the client.
8.If hostname is "exit", terminate the connection.
9.Ping the received hostname.
10.Send the ping result back to the client.
11.Close the connection.
12.Stop the program.

Algorithm: Client Ping Request Program

1.Start the program.
2.Import socket module.
3.Create a socket.
4.Connect to the server at localhost port 8000.
5.Ask the user to enter a hostname or IP address.
6.Send the hostname to the server.
7.Receive the ping result from the server.
8.Display the result.
9.If user enters "exit", close the connection.
10.Stop the program.

## Program

## server.py
```
import socket
from pythonping import ping

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Server listening on port 8000...")
c, addr = s.accept()
print(f"Connection from {addr}")

while True:
    try:
        hostname = c.recv(1024).decode('utf-8')
        if not hostname or hostname.lower() == 'exit':
            print("Client disconnected.")
            break
        response = ping(hostname, verbose=False, count=4)
        c.send(str(response).encode('utf-8'))
    except Exception as e:
        c.send(f"Ping failed: {e}".encode('utf-8'))

c.close()
```
## client.py
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    ip = input("Enter the website you want to ping (or type 'exit' to quit): ")
    s.send(ip.encode('utf-8'))
    if ip.lower() == 'exit':
        break
    print(s.recv(4096).decode('utf-8'))

s.close()
```
## Output

## Server
<img width="783" height="156" alt="image" src="https://github.com/user-attachments/assets/35748a0e-85eb-4129-a78e-6c4d0abb5469" />

## Client
<img width="752" height="391" alt="image" src="https://github.com/user-attachments/assets/e74f3086-2a84-4f71-84de-b0a18a680b84" />

## traceroute

<img width="1241" height="626" alt="image" src="https://github.com/user-attachments/assets/bb651361-aecb-49dc-9549-5697aeda88ee" />

## ipconfig

<img width="987" height="816" alt="image" src="https://github.com/user-attachments/assets/763c6659-b165-44f1-963e-de0109e5cbda" />

## nslookup

<img width="688" height="721" alt="image" src="https://github.com/user-attachments/assets/8ae5bfc8-a772-4323-9e86-3739fdf6d49c" />

## netstat

<img width="1503" height="809" alt="image" src="https://github.com/user-attachments/assets/e9903989-2dca-49d4-b5d7-d6ffd1adb0d8" />

## tcpdump

<img width="1536" height="941" alt="image" src="https://github.com/user-attachments/assets/cfca0b3a-89d0-4e24-963d-8972f1aa4825" />


## Result
Thus Execution of Network commands Performed 
