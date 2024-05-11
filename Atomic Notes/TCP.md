Tags: [[Network]] [[Network Protocols]]
# TCP

**Transmission Control Protocol**

An internet communication protocol that allows two devices to form a connection and stream data.

> [!info] 
> TCP isn't limited to two devices. The underlying network infrastructure can handle routing data packets across multiple devices.

Uses a **three-way handshake** process:
1. The device sends a *synchronize* (*SYN*) request to a server.
2. The server responds with a *SYN/ACK* packet to *acknowledge* receipt of the device's request.
3. The device *acknowledges* the response of the server and sends an *ACK* packet to the server until the last one, then server and device establish a reliable connection.

Occurs at the [[Transport Layer - OSI|transport layer]].

Contains the [[Port|port]] number of the intended destination service.

---
# References

1. Google Cybersecurity Professional Certificate

---
# Flashcards

Flashcard Tags: #network 

An internet communication protocol that allows two devices to form a connection and stream data.
?
TCP
<!--SR:!2024-06-01,21,270-->

What does TCP stands for?
?
Transmission Control Protocol
<!--SR:!2024-05-19,8,270-->

What is the process of a three-way handshake in TCP?
?
1. Client sends synchronize (SYN) request to server.
2. Server responds with SYS/ACK to acknowledge the request.
3. Client acknowledges the SYS/ACK server response to establish a reliable connection.
<!--SR:!2024-05-20,9,272-->