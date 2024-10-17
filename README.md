# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
Client

import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
while(i<len(l)):
st+=s
c.send(str(l[i:st]).encode())
ack=c.recv(1024).decode()
if ack:
print(ack)
i+=s

Server

Thus, python program to perform stop and wait protocol was successfully executed
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
print(s.recv(1024).decode())
s.send("acknowledgement received from the server".encode())
```

## OUPUT
![WhatsApp Image 2024-10-17 at 12 36 39_efd51ca8](https://github.com/user-attachments/assets/ed263f81-4e80-4b2b-b4ca-bf600efed5cd)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
