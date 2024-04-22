# 2a_Stop_and_Wait_Protocol
## Name : Nithish R
## Reg No : 212223040135
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
## client:
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
   break
```
## server:
```
   import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## client:
![image](https://github.com/Magathi7/2a_Stop_and_Wait_Protocol/assets/144870480/0f77e997-d205-445e-83a0-8f01a5f29910)
## server:
![image](https://github.com/Magathi7/2a_Stop_and_Wait_Protocol/assets/144870480/6f299774-4a30-4daf-aef5-71959f95823a)
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
