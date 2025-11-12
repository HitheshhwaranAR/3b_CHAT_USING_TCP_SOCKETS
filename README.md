# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
### Client 
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")
    if not msg:
        break
    s.send(msg.encode())
    print("Server >", s.recv(1024).decode())

s.close()
```
### Server
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Server is listening...")

c, addr = s.accept()
print("Connected with:", addr)

while True:
    clientMessage = c.recv(1024).decode()
    if not clientMessage:
        break
    print("Client >", clientMessage)

    msg = input("Server > ")
    c.send(msg.encode())

c.close()
s.close()

```
## OUPUT
### Client
<img width="1367" height="664" alt="image" src="https://github.com/user-attachments/assets/71ca703d-83d0-465b-a8e8-94facb04c4f1" />
### Server
<img width="1362" height="643" alt="image" src="https://github.com/user-attachments/assets/c34ad501-be91-49ce-9988-37da080571d3" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully created and executed.
