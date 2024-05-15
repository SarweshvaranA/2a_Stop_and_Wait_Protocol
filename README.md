# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:

### client.py
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
    print(ack)
    continue
else:
    c.close()
```
### server.py
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```

## OUTPUT:
### client.py
![image](https://github.com/SarweshvaranA/2a_Stop_and_Wait_Protocol/assets/146930981/c68f9a56-c680-4875-86c4-1b80b9011a79)
### server.py
![image](https://github.com/SarweshvaranA/2a_Stop_and_Wait_Protocol/assets/146930981/ded5c92e-07b3-4ccf-9760-8c6cd3183273)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
