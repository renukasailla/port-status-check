import socket

def check_port(host, port):
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.settimeout(2)

    result = s.connect_ex((host, port))

    if result == 0:
        print(f"Port {port} is OPEN on {host}")
    else:
        print(f"Port {port} is CLOSED on {host}")

    s.close()

# User Input
host = input("Enter Host (e.g., google.com or localhost): ")
port = int(input("Enter Port Number: "))

check_port(host, port)