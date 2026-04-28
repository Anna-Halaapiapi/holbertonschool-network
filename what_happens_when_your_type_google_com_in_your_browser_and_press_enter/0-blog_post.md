# What happens when you type https://www.google.com in your browser and hit Enter?
---

## DNS Request
Your browser sends a request to a DNS Server to resolve the domain www.google.com and translate it into a computer readable IP address.

## TCP/IP
The browser then establishes connection to the IP address via the Transmission Control Protocol (TCP). Prior to any data transmission between client and server, a three way handshake is performed (SYN, SYN-ACK and ACK) to ensure reliability of data transferred between client and Google's server over the internet.

## Firewall
Firewalls on both the client and server sides inspect the data packets transferred between them. The client's firewall will inspect outgoing packets, Google's firewall will inspect the incoming packets, blocking any suspicious traffic before entering Google's network.

## HTTPS/SSL
After the TCP connection is opened, the client's browser will verify Google's SSL certificate, and once verified, all further data transmissions will be encrypted per HTTPS.

## Load Balancer
Google's infrastructure runs load balancers to distribute incoming traffic between thousands of servers. The load balancer routes the incoming request from the client to an available server based on factors such as server health, current load and proximity.

## Web Server
Google's chosen server's web server will receive the HTTPS request, providing static webpage content if sufficient, else for dynamic requests it will further forward the request on to the application server.

## Application Server
The application server will receive the HTTPS request from the web server if business logic is required to run, such as processing a search query or providing account data.

## Database
The database will receive requests to fetch or store data from the application server, such as updating or provding user account details.
Results are then returned up the chain and the browser renders the results.

## Everything's better with a pretty diagram
[!Diagram](./diagram.png)