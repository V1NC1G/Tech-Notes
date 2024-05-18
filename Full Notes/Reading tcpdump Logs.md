# Reading tcpdump logs

> [!note] 
> This reading explains how to identify a brute force attack using tcpdump.

```
14:18:32.192571 IP your.machine.52444 > dns.google.domain: 35084+ A? yummyrecipesforme.com. (24)

14:28:32.2043888 IP dns.google.domain > your.machine.52444: 35084 1/0/0 A 203.0.113.22 (40)
```

`your.machine.52444` is the source computer using port `52444` sending a **DNS resolution request** to the DNS server `dns.google.domain` for the destination URL `yummyrecipesforme.com`. The reply from the DNS server then comes back to the source computer with the **IP address of the destination URL** `203.0.113.22`

