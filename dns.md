# DNS

- Core Function: Think of the Domain Name System (DNS) as a giant, constantly updated address book for the internet. It translates the human-friendly domain names we type into our browsers (like [www.example.com](https://www.example.com)) into numerical IP addresses (like 192.168.1.10) that computers use to locate and talk to each other. Websites, email servers, and pretty much any device on the internet rely on DNS.

## The Hierarchical Structure

- Root Servers

  - At the very top of the DNS hierarchy are the root servers. These are like the master index that knows where to start looking for specific locations.

- TLD Servers

  - Top-Level Domain (TLD) servers manage the 'last part' of a domain name (.com, .org, .net, country codes like .uk, etc.). If you want to find [www.example.com](https://www.example.com), the DNS system knows which TLD server (.com in this case) to ask.

- Authoritative Nameservers
  - These are the final stop. They hold the actual records that map a specific domain name (like [www.example.com](https://www.example.com)) to its corresponding IP address.

## How DNS Works

1. The Query: When you type a domain name like [www.example.com](https://www.example.com) into your browser, your computer first checks its own local DNS cache (like a mini address book). If it doesn't have an entry, the query goes to your configured DNS resolver.

2. The DNS Resolver: This is usually operated by your Internet Service Provider (ISP). It asks the root servers for help: "Hey, where can I find information about .com domains?"

3. Following the Trail: The root server directs the resolver to the .com TLD server. The resolver then asks the TLD server, "Ok, where do I find information about example.com?".

4. Reaching the Destination: The TLD server points the resolver to the authoritative nameserver for example.com. This nameserver finally gives the answer: "[www.example.com](https://www.example.com) maps to the IP address 192.168.1.10".

5. Browsing Time: Your computer now knows how to reach the server behind [www.example.com](https://www.example.com), and your browser can connect and load the website

---

### Extra

- Caching: DNS resolvers and your computer cache DNS information, so looking up the same website repeatedly is quick.
- Redundancy: DNS is a distributed system, meaning that there are many copies of this address book. This makes it incredibly resilient in case one server fails.
- DNS Records: Authoritative nameservers store various types of DNS records beyond simple IP address lookups (A records). These include MX records for email, TXT records for verification, and more.

## Diagrams

![](/images/dns-01.png)

![](/images/dns-02.gif)

![](/images/dns-03.webp)
