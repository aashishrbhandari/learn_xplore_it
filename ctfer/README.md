## Basic Check for a CTF


#### What is This all about?
- I have seen that their are few things that we need to do in a CTF challenge.
- ENUMERATION is a very indepth process.
- I am just doing some automation to get intial details.
- So that it can save your time.
- This is created so that you do not forget the basic checks and get useto it.
- It is just to remind you about the basic things to do


#### CheckList
- Enumeration
<i> [Note: Many of the default are already applied by the NMap Scan] </i>
    - NMAP
        - Get the Port and Service Listing Table
        - Links
            - [My Own NMap Info](https://github.com/aashishrbhandari/learn_xplore_it/blob/master/nmaper/README.md)
        - Example Command Chain To Use:
            [Quick One's]
            - \# `nmap --min-rate 5000 -p- -Pn -n -sS -T5 192.168.232.120` Scan IP and get the Open Port List.
            - \# `nmap -A -p22,80,443 192.168.232.120` Use the Previous Command Open Port List and Gather More Detailed Info Using -A ,-p[Change the Port]

- Going a Step Further in Checking Default Cases
<i> [Note: Many of the default are already applied by the NMap Scan] </i>
    - Get More Details about Each Running Service
        - Check for Default Creds.
        - Create a Table of Important Data Found during Initial Access via Default or Brute Force.
        - These Credentails, Info are useful later on.
        - Gather any CVE based on the Version discovered in previous step

- Exploring
<i> [Note: Always First Go Ahead with Default Creds for Any Auth, Secondly try few more common user & password check] </i>
<i> [Note: Gather Info Related No of Users,] </i>
    - FTP
    - SSH
    - Telnet
    - Mail (SMTP: 25 [or Port 26](https://www.elastic.co/guide/en/siem/guide/current/smtp-on-port-26-tcp.html),465,587; IMAP: 143,993; POP: 110,995)
    - Web Apps (Default 80, 443; Tomcat: 8080, Proxy: 8080)
        <i> [Note: This Info Can Help you learn about the Tech Stack of the WebApp, Nodejs, Python, PHP, ASP(C#,VB), Simple Apache/Nginx/Other Web Server, CGI-Scripts] </i>
        - Basic Check 
            - Use <b> `Wappalyzer` </b> & Gather Initial Details About Tech Stack
            - robots.txt (if Apache)
            - <b> `DevTools` </b>
                - Check Console, Network, Cookies (if Any)
                - Check Source to see any hint or Info in Response Body/HTML,JS,CSS Content
            - Check Request & Response Headers
            - Check using Curl (Some Quick Automation)
        - <u> <b> Just Explore the Web App </b> </u>: Understand how it was created, create a quick roadmap of the WebApp
        - Go Ahead wth GoBuster with Simple Dir Check
            - \# gobuster -u http://10.10.0.1/ -w /usr/share/dirbuster/Web-Contents/list-smal.2-1.txt -t 100
            - \# gobuster -u http://10.10.0.1/ -w /usr/share/dirbuster/Web-Contents/files-list.txt -t 100 -x php,sh,cgi,jsp,py
        - Functionality Based
            - Auth/Login
                - Brute Forcing
                - SQL Injection
            - Upload
                - Check Where the File gets Uploaded
                - Try Basic Bypassing or alteast understand what cannot be done & can be done
                - Upload Respective Language File
            - Form / Input
                - Do some random data entry to see what happens [Dont't Forget to Check Console and Response Body in Source and Inspect]
                - Try Basic XSS Vector
                - Many Times Server Side Template Injection(SSTI) is Highly Possible
                - Check Form Type: Simple WWW-URL-Encoded(Raw), JSON, XML
                    - In All Cases always try dummy data
                    - XML: XXE, XML Injection
            - Directory/Path Traversal
                - Check for any file that can be downloaded [Containing Sensitive Data `A3`]
                - See if you can read `/etc/passwd` [Whether Traversal can go till Root]
            - File Inclusion (LFI/RFI)
                - See if you can read `/etc/passwd` [Whether Traversal can go till Root]
    - Database (MySQL: 3306; MS SQL Server: 1433; )
    - RDP (Default: 3389 [Windows])
    - NETBIOS (137, 138, 139)
    - SMB (Default 135,445)
    
- Exploring After Getting Inside The System
    - Enum [WindowsEnum/LinuxEnum]
        - Linux [lse.sh](https://github.com/diego-treitos/linux-smart-enumeration)
        - Linux [LinuxEnum.sh](https://github.com/rebootuser/LinEnum)
        - Windows [WindowsEnum.bat](https://github.com/azmatt/windowsEnum/blob/master/windowsEnum.bat)
        - Linux PrivEscal [LinPEAS](https://github.com/carlospolop/PEASS-ng/tree/master/linPEAS)
        - Windows PrivEscal [WinPEAS](https://github.com/carlospolop/PEASS-ng/tree/master/winPEAS)
        - Other
            - https://fareedfauzi.gitbook.io/oscp-notes/windows-post-exploitation/automated-enumeration-script
            - https://github.com/411Hall/JAWS
            - https://sushant747.gitbooks.io/total-oscp-guide/content/privilege_escalation_windows.html
    - Important Checks
        - [GTFOBINS](https://gtfobins.github.io/)
    - Explore [By Yourself]
        - Check Current Dir Files
        - Check Sudo Possibility
