# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
```
import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
now = datetime.now()
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
if ack:
 print(ack)
c.close()
```
## OUPUT - ARP
![image](https://github.com/HareeshrajaR/2c.ARP_RARP_PROTOCOLS/assets/144870459/c381ca5a-14fe-471f-a383-dbbaaa865c06)

## PROGRAM - RARP

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode())
```
## OUPUT -RARP
![image](https://github.com/HareeshrajaR/2c.ARP_RARP_PROTOCOLS/assets/144870459/321060c4-96a0-4c50-a2e7-e755bb664032)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
