## Networking

ISO's OSI model is a Theoretical Modal which was never Implemented
OSI(7 Layers): App, Session, Present, Transport, Network, DataLink, Physical

<details>
    <summary>
       More Details:
    </summary>

    - http://support.microsoft.com/kb/103884

</details>

<br>

TCP/IP is the real world implementation of a networking stack
TCP/IP(4 Layers): App, Transport, Network, DataLink



 

I will try adding Everything that i can cover.

\-------------------------------------------
    Application Layer (Layer7/L7)
\-------------------------------------------
    Transport Layer (Layer4/L4)
\-------------------------------------------
    Network Layer (Layer3/L3)
\-------------------------------------------
    Data Link Layer (Layer2/L2)
\-------------------------------------------
    Physical 
\-------------------------------------------







#### TCP & UDP
##### TCP

<u>Details: </u>
    TCP Headers:
        SrcPort, DstPort, 
        Seq No: , Ack? 
        TCP Flags: 12 (9 in Use 3 Reserved) 
        Nonce, CWR(Congestion Window Reduced), ECN-Echo , Urgent, Ack, Push, Reset, Sync, Fin
        Window Size, Checksum, Urgent Pointer,
        Options, Padding
    ----TCP Data----

##### UDP


#### Flow

















FAQ

<details>
    <summary>
        How Packets Travel from one place to another?
    </summary>

    Packets are converted into 1s and 0s and then converted into electrical signals to transfer to other Device
</details>

<br>


<details>
    <summary>
        All About Hub ?
    </summary>

    [Switch is an SMART Hub]
    Switch, Router and machines Goes this way

    Switch Forwarding table, or Content Addressable Memory (CAM) Table stored in RAM
    IN CAM table there can be multiple hosts on the same interface and interfaces without any host attached

    CAM table has a finite size

    Switches learn new MAC addresses dynamically; they inspect the header of every packet they receive, thus identifying new hosts.

    While routers use complex routing protocols to update their routing rules, switches just use the source MAC address of the packets they process to decide which interface to use when forwarding a packet.

    Forwarding in Switch ---- if there is no entry for the Dest MAC Port switch will forward it to all (Just like HUB)
</details>

<br>

<details>
    <summary>
        All About Switch ?
    </summary>

    [Switch is an SMART Hub]
    Switch, Router and machines Goes this way

    Switch Forwarding table, or Content Addressable Memory (CAM) Table stored in RAM
    IN CAM table there can be multiple hosts on the same interface and interfaces without any host attached

    CAM table has a finite size

    Switches learn new MAC addresses dynamically; they inspect the header of every packet they receive, thus identifying new hosts.

    While routers use complex routing protocols to update their routing rules, switches just use the source MAC address of the packets they process to decide which interface to use when forwarding a packet.

    Forwarding in Switch ---- if there is no entry for the Dest MAC Port switch will forward it to all (Just like HUB)
</details>

<br>

<details>
    <summary>
        Quick Func & Difference between Router & Switches ?
    </summary>

    Switch switches within the Subnet, Router Routes between the Network
    Multiple Switches can be connected to built a Network
    Switches do not Segment Network without VLANs, Routers Do -- But they do not forward packets coming from one interface if the have FF:FF:FFF broadcast MAC address.
</details>

<br>

<details>
    <summary>
        Routing Protocol ?
    </summary>

    The Forwarding Policy of Router is called Routing Protocol

    Routing Protocol are used to determine the best path to reach a network
    A router inspects the destination address of very incoming packet and then forwards it through one of its interfaces

    To choose the right forwarding interface, a router performs a lookup in the routing table, where it finds an IP-to-interface binding. The table can also contain an entry with the default address(0.0.0.0). This entry is used when the router receives a packet whose destination is an unknown.
</details>

<br>


<details>
    <summary>
        `Metric` Value in Routing ?
    </summary>

    Metric value is also important in routing

    The metric is selected according to the channel's estimated bandwidth and congestion
</details>

<br>


<details>
    <summary>
        Layer 2 ?
    </summary>

    
    Hubs & Switches are network devices that forward FRAMES (Layer 2 Packets) on a Local Network
    They work with MAC Addresses

</details>

<br>

<details>
    <summary>
        MAC Addresses ?
    </summary>

    A MAC (Media Access Control) address is also known as the physical address
    MAC expressed in Hex are 48 Bits (6 Bytes)
    
</details>

<br>

<details>
    <summary>
        IP Address & MAC Addresses ?
    </summary>

    IP addresses are the Layer 3 (Network layer) addressing scheme used to identify a host in a network, while MAC addresses uniquely identify a network card (Layer 2).
    
</details>

<br>

<details>
    <summary>
        IP Address & MAC Addresses ?
    </summary>

    IP addresses are the Layer 3 (Network layer) addressing scheme used to identify a host in a network, while MAC addresses uniquely identify a network card (Layer 2).
    
</details>

<br>

<details>
    <summary>
        NMap Quicky (Intermediate) ?
    </summary>

    [To be Reframed]
    -sT -> TCP Connect Scan [Full TCP Handshake]
    -sS -> SYN Scan [Stealth  Scan] A Good IDS will be able to detect it. [Only SYN if SYN+ACK Received send RST]
    [Nmap Default: SYN Scan]

    -sV [-sT + more for detecting version -(banner Grabbing)]

    -Pn [Skip pingscan and treat it as it is alive]

    Firewall Pressence / Network Filtering Presenece

    80/tcp open tcpwrapped
    80/tcp open http? 

    nmap --reason

    
</details>

<br>

