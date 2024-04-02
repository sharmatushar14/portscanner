# Python Port Scanner
This Python script performs a simple port scan on a target host to check for open ports within a specified range. It utilizes multithreading for efficient scanning.

## Features
- Multithreaded port scanning for faster results.
- Allows scanning within a specified port range.
- Provides information on open ports.
- Usage
To use the port scanner, provide the target host and port range as command-line arguments:
python port_scanner.py TargetHost StartPort EndPort
Replace TargetHost with the hostname or IP address of the target system, StartPort with the starting port number, and EndPort with the ending port number.

## How it Works
The Python port scanner works by creating multiple threads to concurrently scan ports within the specified range. It utilizes the socket module in Python to attempt to establish TCP connections to each port on the target host.

## Breakdown of how the script works:

The script defines a myScan function, which attempts to establish a TCP connection to the target host and port using the socket.connect method. If the connection is successful, it prints that the port is open.

The script also defines a threader function, which continuously pulls tasks (port numbers) from a queue and assigns them to worker threads for processing.

The main part of the script initializes a queue and creates multiple threads (up to the specified maximum) to handle port scanning tasks concurrently.

For each port within the specified range, a task is added to the queue.

The worker threads continuously pull tasks from the queue and execute the myScan function to scan the ports.

Once all tasks are completed, the script prints the total time taken for the scan to complete.

This approach allows for efficient scanning of multiple ports simultaneously, reducing the overall scan time.
