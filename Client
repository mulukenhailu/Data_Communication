#client side code
import socket
client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
host = socket.gethostname()
port = 5656
client.connect((host,port))
client_number =  input('Enter a number between 1 and 100: ')
data = []
client_name="Muluken"
data.append(client_name)
data.append(client_number)
data = '.'.join(data)
client.send(data.encode())
while True:
    try:
        message = client.recv(1024).decode()
        server_name, server_number, sum = message.split('.')
        print(f'[CLIENT NAME:] {client_name}')
        print(f'[SERVER NAME:] {server_name}')
        print(f'[SERVER RANDOMLY CHOSEN NUMBER:] {server_number}')
        print(f'[CLIENT CHOSEN NUMBER:] {client_number}')
        print(f'[SUM OF CLIENT AND SERVER NUMBER:] {int(server_number)+int(client_number)}')
    except:
        print('No response from the server connection lost')
        break
    else:
        client.close()
        break
