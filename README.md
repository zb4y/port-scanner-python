# Port Scanner (Python)

This is a simple port scanner built with Python.  
It scans ports from 1 to 1024 on a given target IP or domain.

## 💻 Code

```python
import socket

def scan_ports(target):
    print(f"Scanning {target}...")
    for port in range(1, 1025):
        try:
            sock = socket.socket()
            sock.settimeout(0.5)
            sock.connect((target, port))
            print(f"[+] Port {port} is open")
            sock.close()
        except:
            print(f"[-] Port {port} is closed or unreachable")

if __name__ == "__main__":
    target_ip = input("Enter target IP address or domain: ")
    scan_ports(target_ip)
