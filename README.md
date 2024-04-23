# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME: KABILAN V
## REGISTER NO: 212222100018
## AIM
To implement of sliding window protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## client
```
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
```
## server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
## client
![306670811-feb211f3-3539-4e66-aaef-5ee94bd82563](https://github.com/kabilan22000284/2b_SLIDING_WINDOW_PROTOCOL/assets/123469171/821b6189-2989-4c67-afbb-8f903188a1ed)

## server
![306670887-490be7f8-447c-4b3a-9cc7-59cb57876346](https://github.com/kabilan22000284/2b_SLIDING_WINDOW_PROTOCOL/assets/123469171/4d2857c9-ac95-42d5-ba7b-4fc94fa3c74a)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
