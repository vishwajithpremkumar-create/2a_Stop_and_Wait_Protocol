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
## PROGRAM
```
CLIENT
import socket 
s=socket.socket() 
host='127.0.0.1'
port=8080
s.bind((host,port)) 
s.listen(5) 
c,addr=s.accept()
while True:
    i=input("Enter Ram's script: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack: 
        print(ack) 
        continue
    else: 
        c.close() 
        break

SERVER

import socket 
s=socket.socket() 
host='127.0.0.1'
port=8080
s.connect((host,port)) 
while True:
    print(s.recv(1024).decode())
    s.send("Dialogue Completed.".encode())
```
## OUTPUT
<img width="961" height="236" alt="Screenshot 2026-05-21 094615" src="https://github.com/user-attachments/assets/f4decde6-002b-432d-af19-659d45d7b483" />
<img width="958" height="181" alt="Screenshot 2026-05-21 094635" src="https://github.com/user-attachments/assets/d2df5d2e-3e49-4ca5-9be7-24c94ee30a7b" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
