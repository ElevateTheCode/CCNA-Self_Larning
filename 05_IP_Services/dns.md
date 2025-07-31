# DNS (Domain Name System)

## What is DNS?
The Domain Name System (DNS) is a hierarchical and decentralized naming system for computers, services, or other resources connected to the Internet or a private network. It translates human-readable domain names (e.g., `google.com`) into numerical IP addresses (e.g., `172.217.164.174`).

**Analogy:** DNS is like a phone book for the internet. Instead of memorizing IP addresses, you can just use easy-to-remember domain names.

## The DNS Lookup Process
1.  A user enters a domain name in their browser.
2.  The user's computer sends a query to its configured DNS server.
3.  The DNS server, if it doesn't have the answer in its cache, queries other DNS servers (Root, TLD, Authoritative) until it finds the correct IP address.
4.  The DNS server sends the IP address back to the user's computer.
5.  The user's computer can now connect to the web server using the IP address.

## Configuration on a Cisco Device
For a router or switch to resolve DNS names, you need to configure a DNS server and enable domain lookup.

Router(config)# ip domain-lookup
Router(config)# ip name-server 8.8.8.8

- `ip domain-lookup`: Enables the router to perform DNS lookups.
- `ip name-server 8.8.8.8`: Specifies the DNS server to use (Google's public DNS in this case).

**Verification:**
You can test DNS by pinging a domain name.
Router# ping https://www.google.com/url?sa=E&source=gmail&q=google.com
