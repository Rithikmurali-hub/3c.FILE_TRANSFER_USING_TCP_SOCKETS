# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## Name: RITHIK M
## Register Number: 212225040342
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
fileclient.py
```

import socket

# Create socket
client = socket.socket()

# Connect to server
client.connect(("127.0.0.1", 5555))

# Save file name
save_name = input("Enter name to save file: ")

# Receive data
data = client.recv(1000000)

# Save file
with open(save_name, "wb") as file:
    file.write(data)

print("File received successfully")

# Close connection
client.close()
```
fileserver.py

```

import socket

# Create socket
server = socket.socket()

# Bind IP and port
server.bind(("127.0.0.1", 5555))

# Listen for client
server.listen(1)

print("Server waiting for connection...")

# Accept client
client, addr = server.accept()

print("Connected to:", addr)

# Ask filename
filename = input("Enter file name to send: ")

# Open and send file
with open(filename, "rb") as file:
    data = file.read()
    client.send(data)

print("File sent successfully")

# Close connections
client.close()
server.close()

```
## OUPUT
<img width="996" height="195" alt="Screenshot 2026-11-24 083529" src="https://github.com/user-attachments/assets/41db9f96-16d0-403e-a336-fac4f212ca2f" />
<img width="1011" height="263" alt="Screenshot 2026-11-24 083554" src="https://github.com/user-attachments/assets/e8fff3b8-f9f1-41cd-86c4-6a1f0e7ded5e" />


## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
