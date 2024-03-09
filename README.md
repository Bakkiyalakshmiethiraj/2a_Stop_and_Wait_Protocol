## E.BAKKIYALAKSHMI(212223220012)

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
CLIENT.PY
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

 SERVER.PY
 import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())

## OUTPUT
![Screenshot 2024-03-06 113527](https://github.com/Bakkiyalakshmiethiraj/2a_Stop_and_Wait_Protocol/assets/144870983/bc45e7ea-cd67-423b-8631-5211f7f8994b)
![Screenshot 2024-03-06 113605](https://github.com/Bakkiyalakshmiethiraj/2a_Stop_and_Wait_Protocol/assets/144870983/5900e0bc-69b6-4f77-9499-e2111a5135e4)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
