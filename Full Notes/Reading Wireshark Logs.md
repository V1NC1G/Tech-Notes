# Reading Wireshark TCP/HTTP Log

## Log entry number and time

| **No.** | **Time** |
| ------- | -------- |
| 47      | 3.144521 |
| 48      | 3.195755 |
| 49      | 3.246989 |
This part of the Wireshark TCP log section provided starts at log entry number 47 which is 3.144521 seconds after the logging tool started recording.

This indicates that 47 messages were sent and received by the web server in the 3.1 seconds after starting the log.

## Source and destination IP addresses

| **Source**    | **Destination** |
| ------------- | --------------- |
| 198.51.100.23 | 192.0.2.1       |
| 192.0.2.1     | 198.51.100.23   |
| 198.51.100.23 | 192.0.2.1       |

The source and destination columns contain the source IP address of the machine that is sending a packet and the intended destination IP address of the packet.

## Protocol type and related information

| **Protocol** | **Info**                                        |
| ------------ | ----------------------------------------------- |
| TCP          | 42584->443 [SYN] Seq=0 Win-5792 Len=120...      |
| TCP          | 443->42584 [SYN, ACK] Seq=0 Win-5792 Len=120... |
| TCP          | 42584->443 [ACK] Seq=1 Win-5792 Len=120...      |

The **protocol** column indicates that the packets are being sent using the [[TCP]] protocol.

In the given log file, you will notice that the protocol will eventually change to HTTP once the connection to the web server is successfully established.

The **info** column provides information about the packet. It lists the *source port* followed by an arrow pointing to the *destination port*. 

The next element in the info column is part of the three-way handshake process to establish a connection between to machines which are the **SYN**, **SYN, ACK** and **ACK** packet.

## Normal website traffic

A normal transaction between a website visitor and the web server would be like:

| **No.** | **Time** | **Source**    | **Destination** | **Protocol** | **Info**                                        |
| ------- | -------- | ------------- | --------------- | ------------ | ----------------------------------------------- |
| 47      | 3.144521 | 198.51.100.23 | 192.0.2.1       | TCP          | 42584->443 [SYN] Seq=0 Win-5792 Len=120...      |
| 48      | 3.195755 | 192.0.2.1     | 198.51.100.23   | TCP          | 443->42584 [SYN, ACK] Seq=0 Win-5792 Len=120... |
| 49      | 3.246989 | 198.51.100.23 | 192.0.2.1       | TCP          | 42584->443 [ACK] Seq=1 Win-5792 Len=120...      |
| 50      | 3.298223 | 198.51.100.23 | 192.0.2.1       | HTTP         | GET /sales.html HTTP/1.1                        |
| 51      | 3.348457 | 192.0.2.1     | 198.51.100.23   | HTTP         | HTTP/1.1 200 OK (text/html)                     |

> [!note] 
> Note that the handshake process takes a few milliseconds to complete. Then you can identify the employee's browser requesting the `sales.html` webpage using the HTTP protocol at the application level of the [[TCP-IP Model|TCP/IP Model]]. Followed by the web server responding to the request.

