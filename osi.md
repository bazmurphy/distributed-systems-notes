# OSI Model

The Open Systems Interconnection (OSI) model is a framework for understanding network communication.

It divides the process into seven layers, each with a specific function.

1. The physical layer deals with the physical transmission of data, like cables and signals.

   - Cables: Ethernet cable, fiber optic cable
   - Connectors: RJ-45 (Ethernet connector), USB port
   - Wireless technologies: Bluetooth, Wi-Fi

2. The data link layer manages data packets and ensures error-free transmission between devices on a network.

   - MAC addresses: Unique identifier for network devices
   - Ethernet: Common network protocol for wired communication
   - Wi-Fi standards: IEEE 802.11 (a, b, g, n, ac) for wireless communication

3. The network layer handles addressing and routing data packets across different networks.

   - IP addresses: Unique identifier for devices on the internet (IPv4, IPv6)
   - Routers: Devices that forward data packets across networks
   - Internet Protocol (IP): Core protocol for routing data on the internet

4. The transport layer guarantees reliable data delivery between applications.

   - TCP (Transmission Control Protocol): Guarantees reliable and ordered delivery of data packets
   - UDP (User Datagram Protocol): Offers faster but potentially unreliable data delivery
   - Port numbers: Identify specific applications or services (e.g., port 80 for HTTP)

5. The session layer manages communication sessions between applications.

   - Remote Desktop Protocol (RDP): Allows remote access to another computer
   - Hypertext Transfer Protocol Secure (HTTPS): Establishes secure communication between web browsers and servers
   - SSH (Secure Shell): Provides secure remote access to a server

6. The presentation layer formats data for different applications to understand.

   - JPEG, PNG, GIF: Image formats for storing and transmitting visual data
   - MP3, WAV, AAC: Audio formats for storing and transmitting sound data
   - ASCII, UTF-8: Character encoding standards for representing text data

7. The application layer provides services to user applications, like HTTP for web browsing.

   - HTTP (Hypertext Transfer Protocol): Used for communication between web browsers and servers
   - SMTP (Simple Mail Transfer Protocol): Used for sending emails
   - FTP (File Transfer Protocol): Used for transferring files between computers

---

The OSI model is a conceptual framework, not a specific set of protocols.
However, it helps us understand how different parts of a network work together to enable communication.

---

## Diagrams

![](/images/osi-model-01.png)

![](/images/osi-model-02.jpg)

![](/images/osi-model-03.jpg)
