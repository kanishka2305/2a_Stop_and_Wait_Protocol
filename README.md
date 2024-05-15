# EXP:2a_Stop_and_Wait_Protocol
## AIM :
To write a python program to perform stop and wait protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
```py
Developed By: Kanishka.V.S
Register Number: 212222230061
```
### Client:
```py
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
### Server:
```py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT:
### Client:
![323605421-eb561cf4-e279-4c99-bb10-f608e701ec02](https://github.com/kanishka2305/2a_Stop_and_Wait_Protocol/assets/113497357/32f664f0-b4aa-4995-8d2b-8efbe8db5ddc)

### Server:
![323605624-3cb1211c-6827-4b7c-914f-292990f416fd](https://github.com/kanishka2305/2a_Stop_and_Wait_Protocol/assets/113497357/157cfc23-23ff-4e2d-ba97-a86ad31aeb54)

## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
