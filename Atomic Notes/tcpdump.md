Tags: [[Cybersecurity]] [[Network]] [[Tools]]
# tcpdump

`tcpdump` is a command-line network protocol analyzer.

It provides a brief packet analysis and converts key information about about network traffic into formats easily read by humans. It prints information about each packet directly into the terminal.

It also displays the source [[IP Address]], destination IP address, and [[Port|port]] numbers being used in communications.

## Pros in using `tcpdump`

- Lightweight as it has low memory and CPU usage
- Text based and all commands are executed from the terminal
- Can be installed in other Unix based systems and pre installed on many Linux distributions

## Interpreting `tcpdump` output

![[tcp-dump-output.png|100%|center]]

- **Timestamp**: formatted as HH:MM:SS:ss
- **Source IP**: the packet's origin
- **Source port**: port number where the packet originated
- **Destination IP**: destination IP address the packet is being transmitted to
- **Destination port**: port number the packet is being transmitted to

> [!note] 
> `tcpdump` will attempt to resolve host addresses to hostnames. It will also replace port numbers with commonly associated services that use these ports.

## Common usage

- Capture and view network communications and to collect statistics about the network
- Establish a baseline for network traffic patterns and network utilization metrics
- Detect and identify malicious traffic
- Create customized alerts to send the right notifications when network issues or security threats arises
- Locate unauthorized instant messaging, traffic, or wireless access points.

## How attackers use network protocol analyzers

- Maliciously gain information about a specific network
- Capture data packets that contain sensitive information

---
# References

1. Google Cybersecurity Professional Certificate

---
# Flashcards

Flashcard Tags: 