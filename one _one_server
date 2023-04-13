#server side code that can handle only one client

import socket
import random
server_number = random.randint(1,100)
server= socket.socket(socket.AF_INET, socket.SOCK_STREAM)
print('The Server is Running...')
host = socket.gethostname()
port = 5656
server.bind((host,port))
server.listen(5)
server_name = 'Surafel'
while True:
    conn, addr = server.accept()
    print(f'Connection is established from address {addr}')
    print("Ready to recevie message.....")
    message = conn.recv(1024).decode()
    client_name,client_number = message.split('.')
    client_number = int(client_number)
    if 1<=client_number and client_number<=100:
        message = []
        print(f'[CLIENT NAME:] {client_name}')
        print(f'[SERVER NAME:] {server_name}')
        print(f'[SERVER RANDOMLY CHOSEN NUMBER:] {server_number}')
        print(f'[CLIENT CHOSEN NUMBER:] {client_number}')
        print(f'[SUM OF CLIENT AND SERVER NUMBER:] {client_number + server_number}')
        message.append(server_name)
        message.append(str(server_number))
        message.append(str(sum))
        data = '.'.join(message)
        conn.send(data.encode())
        conn.close()
        break
    else:
        print(f'The provided number:[{client_number}] is not in the given range')
        conn.close()
        break
