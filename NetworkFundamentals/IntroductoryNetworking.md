# **Introductory Network Room**
> [Access room](https://tryhackme.com/room/introtonetworking)
---

### **Introduction**
> Let's get started!
- Answer: `No answer needed`
---

### **The OSI Model: An Overview**
> Which layer would choose to send data over TCP or UDP?
- Answer: `4`
- Explanation: Found in the text presented above the question.

> Which layer checks received packets to make sure that they haven't been corrupted?
- Answer: `2`
- Explanation: Found in the text presented above the question.    

> In which layer would data be formatted in preparation for transmission?
- Answer: `2`
- Explanation: Found in the text presented above the question.    

> Which layer transmits and receives data?
- Answer: `1`
- Explanation: Found in the text presented above the question.    

> Which layer encrypts, compresses, or otherwise transforms the initial data to give it a standardised format?
- Answer: `1`
- Explanation: Found in the text presented above the question.    

> Which layer tracks communications between the host and receiving computers?
- Answer: `5`
- Explanation: Found in the text presented above the question.    

> Which layer accepts communication requests from applications?
- Answer: `7`
- Explanation: Found in the text presented above the question.    

> Which layer handles logical addressing?
- Answer: `3`
- Explanation: Found in the text presented above the question.    

> When sending data over TCP, what would you call the "bite-sized" pieces of data?
- Answer: `Segments`
- Explanation: Found in the text presented above the question.    

> [**Research**] Which layer would the FTP protocol communicate with?
>> **Hint:**: FTP is a protocol used to transfer data between computers. It's often accessed with a special program called an FTP Client.
- Answer: `7`
- Explanation: 
    - Technically, just with the Hint:, we could answer this question. However, if you still don't feel confident, the reason why the FTP protocol belongs to the Application Layer is its functionality. 
    - In order to make a file transfer, we need users to authenticate themselves so that the connection is established and the file can be transfered. For this reason, eve though the FTP protocol has Presentation Layer components and Session Layer components, it is considered an Application Layer Protocol. 

> Which transport layer protocol would be best suited to transmit a live video?
- Answer: `UDP`
- Explanation: Found in the text presented above the question.    
---

### **Encapsulation**
> How would you refer to data at layer 2 of the encapsulation process (with the OSI model)?
- Answer: `Frames`
- Explanation: Found in the text presented above the question.   

> How would you refer to data at layer 4 of the encapsulation process (with the OSI model), if the UDP protocol has been selected?
- Answer: `Datagrams`
- Explanation: Found in the text presented above the question.   

> What process would a computer perform on a received message?
- Answer: `De-encapsulation`
- Explanation: Found in the text presented above the question.   

> Which is the only layer of the OSI model to add a *trailer* during encapsulation?
- Answer: `Data Link`
- Explanation: Found in the text presented above the question.   

> Does encapsulation provide an extra layer of security (**Aye**/**Nay**)?
- Answer: `Aye`
- Explanation: Found in the text presented above the question.   
---

### **The TCP/IP Model**
> Which model was introduced first, OSI or TCP/IP?
- Answer: `TCP/IP`
- Explanation: Found in the text presented above the question. 

> Which layer of the TCP/IP model covers the functionality of the Transport layer of the OSI model (**Full Name**)?
- Answer: `Transport`
- Explanation: Found in the text presented above the question. 

> Which layer of the TCP/IP model covers the functionality of the Session layer of the OSI model (**Full Name**)?
- Answer: `Application`
- Explanation: Found in the text presented above the question. 

> The Network Interface layer of the TCP/IP model covers the functionality of two layers in the OSI model. These layers are Data Link, and?.. (**Full Name**)?
- Answer: `Physical`
- Explanation: Found in the text presented above the question. 

> Which layer of the TCP/IP model handles the functionality of the OSI network layer?
- Answer: `Internet`
- Explanation: Found in the text presented above the question. 

> What kind of protocol is TCP
>> **Hint:** In comparison, UDP would be connectionless
- Answer: `Connection-based`
- Explanation: Found in the text presented above the question. 

> What is SYN short for?
>> **Hint:** British Spelling
- Answer: `Synchronise`
- Explanation: Found in the text presented above the question. 

> What is the second step of the three-way handshake?
- Answer: `SYN/ACK`
- Explanation: Found in the text presented above the question. 

> What is the short name for the "Acknowledgement" segment in the three-way handshake?
- Answer: `ACK`
- Explanation: Found in the text presented above the question. 
---

### **Networking Tools - Ping**
> What command would you use to ping the `bbc.co.uk` website?
- Answer: `ping bbc.co.uk`

> Ping `muirlandoracle.co.uk`. What is the IPv4 address?
>> **Hint:** You may need to answer question 4 first and use that switch to resolve the IPv4 address of the site, rather than the IPv6 address.
- Answer: `217.160.0.152` 
- Note: ping the URL yourself to make sure the IP is still the same. 

> What switch lets you change the interval of sent ping requests?
>> **Hint:** Look in the man page
- Answer: `-i` 
- Explanation: 
  - In your AttackBox or in your local machine, type `man ping` or `ping --help` to find a list of *ping* arguments and its description.

> What switch would allow you to restrict requests to IPv4?
- Answer: `-4` 
- Explanation: 
  - In your AttackBox or in your local machine, type `man ping` or `ping --help` to find a list of *ping* arguments and its description.
  
> What switch would give you a more verbose output?
- Answer: `-v` 
- Explanation: 
  - In your AttackBox or in your local machine, type `man ping` or `ping --help` to find a list of *ping* arguments and its description.
---

### **Networking Tools - Traceroute**
> Use traceroute on `tryhackme.com`. Can you see the path your request has taken?
- Answer: `No answer needed` 
  
> What switch would you use to specify an interface when using Traceroute?
>> **Hint:** An interface is provided by your NIC -- common interfaces are things like tunnels for VPN connections, ethernet connections, and wireless connections
- Answer: `-i` 
- Explanation: 
  - In your AttackBox or in your local machine, type `man traceroute` or `traceroute --help` to find a list of *traceroute* arguments and its description.

> What switch would you use if you wanted to use TCP SYN requests when tracing the route?
- Answer: `-T` 
- Explanation: 
  - In your AttackBox or in your local machine, type `man traceroute` or `traceroute --help` to find a list of *traceroute* arguments and its description. In case you do not find the answer there, it means the manual page is not up to date, but you can check it out [here](https://linux.die.net/man/8/traceroute).

> [Lateral Thinking] Which layer of the TCP/IP model will traceroute run on by default (Windows)?
- Answer: `internet` 
- Explanation: 
  - We know that by default, the `tracert` operates using the same ICMP protocol that *ping* utilises. The ICMP protocol used by *ping* runs on the Network Layer (OSI), therefore, it also runs on the Network Layer (OSI), which is equivalent to the Internet Layer (TCP/IP).
---

### **Networking Tools - WHOIS**
> Perform a whois search on `facebook.com`
- Answer: `No answer needed`

> What is the registrant postal code for `facebook.com`?
- Answer: `94025`
- Explanation:
  - After executing `whois facebook.com` we get a bunch of info regarding `facebook.com`. Right after `Domain Status` we get a list of `Registrant` data, such as the `Postal Code`.  

> When was the facebook.com domain first registered?
- Answer: `20/03/1997` 

> Perform a whois search on `microsoft.com`
- Answer: `No answer is needed`

> Which city is the registrant based in?
- Answer: `Redmond`

> [**OSINT**] What is the name of the golf course that is near the registrant address for `microsoft.com`?
- Answer: `Bellevue Golf Course`
- Explanation:
  - This one is a bit harder, once distance definition is quite personal and not all maps recognize the registrant address or are not fully updated. However, with a bit of research we get to `Bellevue Golf Course`.

> What is the registered Tech Email for microsoft.com?
- Answer: `msnhst@microsoft.com`
---

### **Networking Tools - Dig**
> What is DNS short for?
- Answer: `Domain Name System`
- Explanation: Found in the text presented above the question. 

> What is the first type of DNS server your computer would query when you search for a domain?
- Answer: `Recursive`
- Explanation: Found in the text presented above the question. 

> What type of DNS server contains records specific to domain extensions (.com, .co.uk, etc)? Use the long version of the name.
- Answer: `Top-Level Domain`
- Explanation: Found in the text presented above the question.

> Where is the very first place your computer would look to find the IP address of a domain?
- Answer: `Local Cache`
- Explanation: Found in the text presented above the question.

> [**Research**] Google runs two public DNS servers. One of them can be queried with the IP 8.8.8.8, what is the IP address of the other one?
- Answer: `8.8.4.4`
- Explanation: Find the answer [here](https://developers.google.com/speed/public-dns/).

> If a DNS query has a TTL of 24 hours, what number would the dig query show?
- Answer: `86400`
- Explanation: 
  - TTL stands for Time To Live, it represents the amount of time in seconds the DNS caching is valid. That is, when the computer should request the IP for a certain URL again.