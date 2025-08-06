🌐 The OSI Model

The Open Systems Interconnection (OSI) model is a conceptual framework used to understand how data travels from one computer to another. It has 7 layers.

1.  **Physical Layer (Layer 1):** Deals with the physical medium, such as cables, connectors, and electrical signals. (e.g., Ethernet cables, Hubs)
2.  **Data Link Layer (Layer 2):** Provides node-to-node data transfer. It uses MAC addresses for addressing and is responsible for error detection. (e.g., Switches, MAC addresses, Frames)
3.  **Network Layer (Layer 3):** Handles logical addressing (IP addresses) and routing of data packets across networks. (e.g., Routers, IP addresses, Packets)
4.  **Transport Layer (Layer 4):** Manages end-to-end communication, including reliability and flow control. Uses TCP and UDP protocols. (e.g., TCP, UDP, Segments)
5.  **Session Layer (Layer 5):** Establishes, manages, and terminates connections (sessions) between applications.
6.  **Presentation Layer (Layer 6):** Translates, encrypts, and compresses data. It ensures data is in a usable format for the application layer.
7.  **Application Layer (Layer 7):** The layer users interact with. Provides network services to end-user applications. (e.g., HTTP, FTP, DNS)

## 🌐 The TCP/IP Model

The TCP/IP model is the practical protocol suite used on the internet. It has 4 layers (sometimes described as 5).

1.  **Network Access / Link Layer:** Combines the OSI Physical and Data Link layers. (e.g., Ethernet)
2.  **Internet Layer:** Corresponds to the OSI Network layer. Responsible for logical addressing and routing. (e.g., IP, ICMP)
3.  **Transport Layer:** Same as the OSI Transport layer. Provides end-to-end communication. (e.g., TCP, UDP)
4.  **Application Layer:** Combines the OSI Session, Presentation, and Application layers. (e.g., HTTP, DNS, FTP)

**Analogy:**
Imagine shipping a letter.
- **Application:** You write the letter (the data).
- **Presentation:** You choose the language and formatting.
- **Session:** You start the process of sending it.
- **Transport:** You decide to use a registered service (TCP) or standard mail (UDP).
- **Network:** The post office decides the path (route) for your letter.
- **Data Link:** The local mail truck delivers it to the next sorting facility.
- **Physical:** The truck itself, the roads, and the movement.
