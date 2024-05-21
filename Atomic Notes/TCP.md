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

Flashcard Tags: 