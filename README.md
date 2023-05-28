# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

DATE :06\03\2023

AIM : To write a python program to perform stop and wait protocol


ALGORITHM :
```
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
6. Stop the program
```

PROGRAM :
```
CLIENT:
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
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```

OUTPUT:

![Screenshot (44)](https://github.com/ArpanBardhan/19CS406-EX-1/assets/119405037/af7a594f-4d29-48c4-a249-4cd89e87fc2d)
![Screenshot (45)](https://github.com/ArpanBardhan/19CS406-EX-1/assets/119405037/13dcb56e-79be-46cc-b8f5-4ff696300767)



RESULT: Thus, python program to perform stop and wait protocol was successfully executed.

