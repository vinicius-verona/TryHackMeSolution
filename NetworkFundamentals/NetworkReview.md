# **Network Review**
> A Network Intro Review 
---

## **OSI Model**
> OSI stands for "Open System Interconnection".
- The OSI Model is a standardised model used to demonstrate the computer networking theory.
- It consists of 7 layers, these are:


| Name | Layer |
| :--: | :--: |
|`Application` | (7th layer) |
|`Presentation` | (6th layer) |
|`Session` | (5th layer) |
|`Transport` | (4th layer) |
|`Network` | (3rd layer) |
|`Data Link` | (2nd layer) |
|`Physical` | (1st layer) |

<br>

### **Application**
- This is the most "external" layer, it consists of a real application, i.e. the interface used to gather the data that will be transmitted, e.g. `Netflix`.

### **Presentation**
- Receives data from the previous layer. Once the `application` layer does not have a standardised data format, the other computer (receivig one) might not understand it. Therefore the `presentation` layer will translate it to a standard format.
- The 6th layer also handle any encryption, compression or transformations necessary.

### **Session**
- This layer is responsible for trying/maintaining the connection established with the other machine. Every session is `unique` for a specific communication, thus we can make multiple requests to different endpoints (destine machine) without having the data altered/mixed. 
- In case the connection can be established, the `session` layer sends the data to the 4th layer.

### **Transport**
- One of its tasks, is to choose which protocol will be used to transmit the data. 
- Once the protocol has been chosen, the `transport` layer divides the transmission into bit-sized pieces in order to favor the transmission.
- The most common protocol are:
  - **TCP** - Transmission Control Protocol is a connection-based transmission which favor the quality of its transfer over speed, i.e. it ensures that no data is lost during the transfer once both computers are in constant communication. It is worth reminding that it does not mean it will be a slow data transfer, it happens with an acceptable speed. 
    - Its bit-sized pieces are called *`segments`*
  - **UDP** - User Datagram protocol is the opposite of **TCP**, it favors the speed over quality of transmission. Usually it is used for streaming, i.e. when the speed is more important that the accuracy of its data. This is the reason why videos stream might lose image quality.  
    - Its bit-sized pieces are called *`datagrams`*
  - **SMB** - Server Message Block Protocol is a client-server communication protocol used for sharing access to files, ports, printers, etc. 
    - This protocol is known as a response-request protocol, i.e. it transmits multiple messages between the server and client in order to establish a connection. The client must connect to the server using `TCP/IP`, `NetBEUI` or `IPX/SPX`.
    - Once they have established a connection, clients can send a command (SMB) to the server allowing them to access shares, read and write files, and generally do all the sort of things that you want to do with a file system. However, in the case of SMB, these are done over the network.

### **Network**
- This layer is the one that will locate the destination of our request. It takes the IP (Logical Addressing) address of a page (for example) and decide which route it should take to send the request.
- The most common logical addressing is the IPV4 format.

### **Data Link**
- After receiving the packet from the `network` layer (containing the IP address for the remote machine), it adds the MAC address of the receiving endpoint (the physical address)
  - `MAC` stands for `Media Access Control`. Every computer with network interface has a `NIC`, i.e. Network Interface Card in which there is a unique `MAC` address to identify it.
- This layer is also the one responsible to translate the packet to a format suitable for transmission.
- When a computer receives a packet after a transmission, this layer will make sure it has not been corrupted.

### **Physical**
- The most "internal" layer, it consists purely of hardware. 
- Here, the electrical pulses are sent and received. It is its job to translate the binary data to electrical signals and also the opposite.
---
## **Encapsulation**
- As data is sent from one layer to the next, more information containing specific details is added. 
- From `layer 7` to `layer 3`, the added piece is called `Header` which contain information from that specific layer, e.g. IP addresses, protocol being used, etc. The `Data Link` layer, also includes a `Header`, however, it adds to the end of the piece a `Trailer`, which is used to verify that the data has not been corrupted while its transmission.
- This `Trailer` also adds some security level, once the data cannot be altered without breaking the `Trailer`.
- The opposite process is called de-encapsulation and happens when the data is received from another computer.
- It is worth mentioning that the encapsulated data is given a different name at different steps of the process. These are:

| Name | Layer |
| :--: | :--: |
|`Data` | (7th layer) |
|`Data` | (6th layer) |
|`Data` | (5th layer) |
|`Data (Segments/Datagrams)` | (4th layer) |
|`Data (Packets)` | (3rd layer) |
|`Data (Frames)` | (2nd layer) |
|`Data Stream (Bits)` | (1st layer) |

<br>

---

## **TCP/IP Model**
- Quite similar to the `OSI Model`, however, a bit older. It consists of 4 layers. These are:

| Name | Layer |
| :--: | :--: |
|`Application` | (4th layer) |
|`Transport` | (3rd layer) |
|`Internet` | (2nd layer) |
|`Network Interface` | (1st layer) |

<br>

- Comparing both models we have the following match per layer:

<table>
    <thead>
      <tr>
        <th>TCP/IP</th>
        <th>OSI</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td rowspan=3>Application</td>
        <td>Application</td>
      </tr>
      <tr><td>Presentation</td></tr>
      <tr><td>Session</td></tr>
      <tr>
        <td>Transport</td>
        <td>Transport</td>
      </tr>
      <tr>
        <td>Internet</td>
        <td>Network</td>
      </tr>
      <tr>
        <td rowspan=2>Network Interface</td>
        <td>Data Link</td>
      </tr>
      <tr><td>Physical</td></tr>
    </tbody>
</table>

<br>

- The processes of encapsulation and de-encapsulation work in exactly the same way with the TCP/IP model as they do with the OSI model. At each layer of the TCP/IP model a header is added during encapsulation, and removed during de-encapsulation.
- The TCP/IP takes its name from two protocols, the TCP and IP (Internet Protocol). The TCP controls the flow of data between the two endpoints, and the IP controls how the packet is addressed.
- The proccess of connection using the TCP protocol is known as a *`three-way handshake`*. First of all, the source computer will send a request to the remote server, this request indicates that it wants to start a connection. This request contains something called a SYN (short for synchronise) bit, which essentially makes first contact in starting the connection process.The server will respond the request with a packet containing the SYN bit, as well as another "acknowledgement" bit, called ACK. Finally, the source computer will send a packet that contains the ACK bit by itself, confirming that the connection has been setup successfully. With the three-way handshake successfully completed, data can be reliably transmitted between the two computers. Any data that is lost or corrupted on transmission is re-sent, thus leading to a connection which appears to be lossless.

---
## **DNS**
- DNS stands for Domain Name System, it works like a phonebook, it converts the URL typed into an IP address. The DNS is a TCP/IP protocol and the way it works is simple, when the user send a request to a specific URL, then computer will firstly look for the IP in the DNS server cache, if it hasn't been found, it will then send a request to a DNS server (already known by the computer) and wait for the response by the server. Once our computer knows the URL's IP address, the transmission proccess continues. 
- Okay, but, how does it really work? 
  - If the IP have not been found in the cache, the DNS server will send a query to one of the [**13 root name DNS servers**](https://en.wikipedia.org/wiki/Root_name_server). 
  - The root server will then return the list of [**Top-level domain**](https://en.wikipedia.org/wiki/Top-level_domain), e.g. a list of DNS servers that handle ".com" domains. 
  - Now the DNS server we sent our request will send a query to one of the servers in the list, which will return the [**authoritative name server**](https://www.cloudns.net/blog/authoritative-dns-server/) where the desired domain is stored. 
  - Finally, a final query is sent to the auhoritative name server which will return the IP address we are looking for.
- Want to read more about DNS?
  - [**DNS Root Servers: What Are They and Are There Really Only 13?**](https://securitytrails.com/blog/dns-root-servers)
  - [**How DNS Works: Domain Name System Terminology**](https://cloudacademy.com/blog/how-dns-works/)
  - [**What is DNS?**](https://www.cloudflare.com/learning/dns/what-is-dns/)
---

## **Future Reading**
-  **CISCO Self Study Guide by Steve McQuerry**
-  **Cryptography and Network Security: Principles and Practice by William Stallings**