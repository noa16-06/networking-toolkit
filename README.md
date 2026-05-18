# Network Tools

A collection of Python networking utilities for TCP, UDP, and advanced socket communication.

## Tools

### tcp-server.py
A simple TCP server that listens for incoming connections and echoes acknowledgment.

**Features:**
- Listens on all interfaces (`0.0.0.0`) on port 9998
- Accepts multiple connections using threading
- Receives data from clients and sends `ACK` response

**Usage:**
```bash
python tcp-server.py
```

### tcp-client.py
A basic TCP client that connects to a remote host and sends HTTP requests.

**Features:**
- Connects to HTTP servers (default: www.google.com:80)
- Sends HTTP GET requests
- Receives and prints responses

**Usage:**
```bash
python tcp-client.py
```

### udp-client.py
A UDP client for sending and receiving datagram packets.

**Features:**
- Sends UDP packets to a target host (default: 127.0.0.1:9997)
- Receives responses from UDP servers
- Configurable target host and port

**Usage:**
```bash
python udp-client.py
```

### netcat.py
A versatile network utility similar to the `nc` (netcat) command. Supports client and server modes with command execution and file upload capabilities.

**Features:**
- **Listen mode** (`-l`): Start a server on specified host/port
- **Connect mode**: Send data to a remote host
- **Command shell** (`-c`): Execute interactive commands
- **Command execution** (`-e`): Run specific commands
- **File upload** (`-u`): Upload files to remote server
- Keyboard interrupt handling

**Usage:**
```bash
# Start listening on port 5555
python netcat.py -t 192.168.1.108 -p 5555 -l

# Connect to remote server
python netcat.py -t 192.168.1.108 -p 5555

# Listen with command shell
python netcat.py -t 192.168.1.108 -p 5555 -l -c

# Execute a command
python netcat.py -t 192.168.1.108 -p 5555 -l -e="cat /etc/passwd"

# Upload a file
python netcat.py -t 192.168.1.108 -p 5555 -l -u=mytest.txt

# Echo data to a server
echo 'ABC' | python netcat.py -t 192.168.1.108 -p 135
```

## Requirements

- Python 3.6+
- Standard library only (no external dependencies)

## Installation

```bash
git clone <repository-url>
cd network-tools
```

## Notes

- Modify default host/port values in each script as needed
- Ensure appropriate firewall rules are in place when using these tools
- These tools are designed for educational and testing purposes

## License

MIT
