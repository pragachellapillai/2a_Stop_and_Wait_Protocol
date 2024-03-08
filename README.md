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
CLIENT:
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
 SERVER:

 ```
   import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT

SERVER:
![WhatsApp Image 2024-03-06 at 15 54 45_b4934533](https://github.com/pragachellapillai/2a_Stop_and_Wait_Protocol/assets/148254952/b92919f6-58f8-4e43-bcce-47b552e1839a)


SERVER:
![WhatsApp Image 2024-03-06 at 15 55 11_2866181f](https://github.com/pragachellapillai/2a_Stop_and_Wait_Protocol/assets/148254952/90a5c336-f2fe-4bdb-b7d1-552cde691429)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
