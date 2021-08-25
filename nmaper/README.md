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

    - No Reply for SYN Packet
    - ICMP Error Recieved
    - ............ 
</details>

<br>


<details>
    <summary>
        2. Quick Difference Between [SYN Scan & TCP Connect Scan]:
    </summary>

    - TCP Connect Syn is Time Consuming
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




