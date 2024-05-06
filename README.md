## 2a_Stop_and_Wait_Protocol
## NAME : DHARANISH MS
## REGISTER NO : 212223240027

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
Client :
```
import socket
s=socket.socket()
s.bind(('localhost', 8000))
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

Server :
```
import socket
s=socket.socket()
s.connect(('localhost', 8000))
while True:
     print(s.recv(1024).decode())
     s.send("Acknowledgement Recived".encode())
```
## OUTPUT
Client :
![client 2a](https://github.com/MSDharanish-23011819/2a_Stop_and_Wait_Protocol/assets/147139454/a68eddd4-a637-4809-bf72-452c3bdd49dd)


Server :
![server 2a](https://github.com/MSDharanish-23011819/2a_Stop_and_Wait_Protocol/assets/147139454/c10878c1-94e0-4199-91e2-fe0a104d87ba)





## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
