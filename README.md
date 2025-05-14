# 2c.SIMULATING ARP /RARP PROTOCOLS

## Name:SAKTHIVEL S
## REG NO: 212223220090
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
Client: 
import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"}; 
while True: 
            ip=c.recv(1024).decode() 
            try: 
                c.send(address[ip].encode()) 
            except KeyError: 
                c.send("Not Found".encode())   
Server:
 
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True:
   ip=input("Enter logical Address : ") 
    s.send(ip.encode()) 
    print("MAC Address",s.recv(1024).decode())
```
## OUPUT - ARP

![442390512-78409509-0e6f-4a40-922d-c285faa54ae0](https://github.com/user-attachments/assets/21e090e7-1d5c-4a70-8295-b4dbdbd22799)


![442390598-88d6fb5c-0206-4a5b-8f10-b6328db6e0d9](https://github.com/user-attachments/assets/453f4d7e-a7ea-4c58-9d73-d6f60d03ead5)

## PROGRAM - RARP
```
Client:
 
import socket 
s=socket.socket() 
s.bind(('localhost',9000)) 
s.listen(5) 
c,addr=s.accept() 
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"}; 
while True: 
            ip=c.recv(1024).decode() 
            try: 
                c.send(address[ip].encode()) 
            except KeyError:
           c.send("Not Found".encode())   
Server:
 
import socket 
s=socket.socket() 
s.connect(('localhost',9000)) 
while True: 
    ip=input("Enter MAC Address : ")   
    s.send(ip.encode()) 
    print("Logical Address",s.recv(1024).decode()) 
```

## OUPUT -RARP

Client:
![442390926-6f816e6a-1f07-4954-8969-6ce710e249bf](https://github.com/user-attachments/assets/e3a51132-7fe3-4c70-a25e-91ba9f5e6571)

Server:

![442390997-26bd74c9-52f4-4675-8842-5c2e710cd1d7](https://github.com/user-attachments/assets/d9ff5316-2953-47e2-ace0-eb6aab8fa408)



## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
