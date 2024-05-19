# Reading tcpdump logs

This reading explains how to identify a brute force attack using tcpdump.

```
14:18:32.192571 IP your.machine.52444 > dns.google.domain: 35084+ A? yummyrecipesforme.com. (24)

14:28:32.2043888 IP dns.google.domain > your.machine.52444: 35084 1/0/0 A 203.0.113.22 (40)
```

`your.machine.52444` is the source computer using port `52444` sending a **DNS resolution request** to the DNS server `dns.google.domain` for the destination URL `yummyrecipesforme.com`. The reply from the DNS server then comes back to the source computer with the **IP address of the destination URL** `203.0.113.22`

```
14:18:36.786501 IP your.machine.36086 > yummyrecipesforme.com.http: Flags [S], seq 2873951608, win 65495, options [mss 65495,sackOK,TS val 3302576859 ecr 0,nop,wscale 7], length 0

14:18:36.786517 IP yummyrecipesforme.com.http > your.machine.36086: Flags [S.], seq 3984334959, ack 2873951609, win 65483, options [mss 65495,sackOK,TS val 3302576859 ecr 3302576859,nop,wscale 7], length 0
```

This section shows the source computer `your.machine.36086` using port `36086`, sends connection request (**Flag [S]**) to the destination **yummyrecipesforme.com.http**.

The **http** suffix signifies the port number which is commonly associated with port **80**.

The reply shows the destination acknowledging the received connection request (**Flag [S.]**)

> [!seealso] 
> [[TCP Flag Codes]]

```
14:18:36.786589 IP your.machine.36086 > yummyrecipesforme.com.http: Flags [P.], seq 1:74, ack 1, win 512, options [nop,nop,TS val 3302576859 ecr 3302576859], length 73: HTTP: GET / HTTP/1.1
```

The log entry code **HTTP: GET / HTTP/1.1** shows the browser is requesting data from **yummyrecipesforme.com** with the **HTTP:GET** method using HTTP protocol version 1.1. *This could be the download request for the malicious file.*

```
14:20:32.192571 IP your.machine.52444 > dns.google.domain: 21899+ A? greatrecipesforme.com. (24)

14:20:32.204388 IP dns.google.domain > your.machine.52444: 21899 1/0/0 A 192.0.2.172 (40)

14:25:29.576493 IP your.machine.56378 > greatrecipesforme.com.http: Flags [S], seq 1020702883, win 65495, options [mss 65495,sackOK,TS val 3302989649 ecr 0,nop,wscale 7], length 0
  
14:25:29.576510 IP greatrecipesforme.com.http > your.machine.56378: Flags [S.], seq 1993648018, ack 1020702884, win 65483, options [mss 65495,sackOK,TS val 3302989649 ecr 3302989649,nop,wscale 7], length 0
```

From the log messages above we can observe that the traffic is routed from the source computer to the DNS server again using port 52444 to make another DNS resolution request.

The DNS server routes the traffic to a new IP address **192.0.2.172** and its associated URL **greatrecipesforme.com.http**. The traffic changes to a route between the source computer and the *spoofed* website (outgoing traffic: **IP your.machine.56378 > greatrecipesforme.com.http** and incoming traffic: **greatrecipesforme.com.http > IP your.machine.56378**).

> [!note] 
> Note that the port number (**.56378**) on the source computer has changed again when directed to a new website.