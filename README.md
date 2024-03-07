# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM:

##SERVER:

```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print('Connected by', addr)
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
##CLIENT:

```
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        message = input("Enter message to send to server: ")
        s.sendall(message.encode())
        data = s.recv(1024)
        print('Received', repr(data.decode()))
```
## OUPUT:

![3a 1](https://github.com/Jeecikasrina23013947/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/148515300/cf732e0e-64d5-430d-b742-f3f46e57343f)

![3a 32](https://github.com/Jeecikasrina23013947/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/148515300/143de2bb-c297-4e0d-ada6-ce58efddc158)


## RESULT:

Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
