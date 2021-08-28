# Nmap 
#### Adding few useful commands which you can use directly when doing Enumeration

### Scan All Ports 
### `#Quickly` `#AllPorts` 

<details>
    <summary>
        What is this
    </summary>

    Do a Quick Enumeration of the target Using NMap.
    - Many Times in CTF/Assessment their are other services as well on ports greater than 1000
    - This command can quickly give you a list of Open Ports and with Predefined Mapping/Info of the Service 
    Running
    - It is Actually Fast. You can try this command with prepended `time` command and see the results
    - I have used them in CTF challenges
</details>

<br>

[Command]

Syntax
Note: You can increase the Speed by adding `-T5`, already done
```bash
nmap --min-rate 5000 -p- -Pn -n -sS -T5 [ip_addr]
```

Example: IP: 192.168.232.120
```bash
nmap --min-rate 5000 -p- -Pn -n -sS -T5 192.168.232.120
```

<details>
    <summary>
        Explanation
    </summary>

    - Packet Sent Rate [--min-rate], 5000 should be Good
    - Check All Ports [-p-]
    - Do Not Ping & Check / Assume Host is Up [-Pn]
    - Do Not Do Reverse lookup etc. [-n]
    - Syn Scan [-sS] [Flow: SYN -> SYN+ACK -> RST]
    - [T5] Get the Maximum speed. Do check without this for diff.
</details>

<br>



### Service Detailed Info
<details>
    <summary>
        What is this
    </summary>

    Use This When Ports are Known, SO that you can Run Detailed Scan on it
</details>

<br>

[Command]

Syntax

```bash
nmap -A -p22,80,443 [ip_addr]
```

Example: IP: 192.168.232.120
```bash
nmap -A -p22,80,443 192.168.232.120
```


Explanation
- OS detection, defaults scripts, TCP Connect Scan [-A]



##FAQ

<details>
    <summary>
        1. When & Why NMap say Port Status as Filtered ?
    </summary>

    [High Presence of Firewall]
    - No Reply for SYN Packet [Firewall Dropped the Packet]
    - ICMP Error Recieved [ICMP error messages]
</details>

<br>

<details>
    <summary>
        2. Quick Difference Between [SYN Scan & TCP Connect Scan]:
    </summary>

    - In SYN scan When the Remote Server Sends SYN+ACK Nmap sends a RST Flag, to discard the 3 Way Handshake, whereas in TCP COnnect SYN it completes the 3 Way Handshake
    - SYN Scan are stealth Scan, since they might not be logged in the Firewall, but Modern Firewall and Next-Gen Firewall, IDPS, IDS, IPS can still detect it. A well configured Firewall, IDPS, IDS, IPS can also detect it.
</details>

<br>

<details>
    <summary>
        3. Can i use them Combined Quickly ?
    </summary>

    - I have combined both and created a micro Py Script to do both in one Go and get detailed Info
    - It is a simple py script.
    - `I am going work on a Better One`
</details>

<br>


<details>
    <summary>
        4. Xmas scan (-sX) ?
    </summary>

    - Sets the FIN, PSH, and URG flags, lighting the packet up like a Christmas tree.
    - `More to Written`
</details>

<br>


<details>
    <summary>
        5. Firewall - Check, Identify, Evasion, Bypassing, Access Control Enum ?
    </summary>

    - Ack Scan (-sA) : The ACK scan probe packet has only the ACK flag set (unless you use --scanflags). When scanning unfiltered systems, open and closed ports will both return a RST packet. Nmap then labels them as unfiltered, meaning that they are reachable by the ACK packet, but whether they are open or closed is undetermined. Ports that don't respond, or send certain ICMP error messages back (type 3, code 0, 1, 2, 3, 9, 10, or 13), are labeled filtered.
    - Fragment Packets (-f) :- Used to fragment the packets (i.e. split them into smaller pieces) making it less likely that the packets will be detected by a firewall or IDS.
    - An alternative to -f, but providing more control over the size of the packets: --mtu <number>, accepts a maximum transmission unit size to use for the packets sent. This must be a multiple of 8.
    - --scan-delay <time>ms:- used to add a delay between packets sent. This is very useful if the network is unstable, but also for evading any time-based firewall/IDS triggers which may be in place.
    - --badsum:- this is used to generate in invalid checksum for packets. Any real TCP/IP stack would drop this packet, however, firewalls may potentially respond automatically, without bothering to check the checksum of the packet. As such, this switch can be used to determine the presence of a firewall/IDS.
</details>

<br>