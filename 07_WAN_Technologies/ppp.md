# PPP (Point-to-Point Protocol)

## What is PPP?
PPP is a data link layer (Layer 2) protocol used to establish a direct connection between two nodes over a serial link. It is commonly used for establishing a WAN connection between a customer's router and a service provider's router.

**Key Features:**
- **Authentication:** Supports authentication protocols like PAP (Password Authentication Protocol) and CHAP (Challenge Handshake Authentication Protocol). CHAP is more secure.
- **Error checking:** PPP has built-in error detection.
- **Protocol multiplexing:** Can encapsulate different types of network layer protocols (e.g., IP, IPX).

## Configuration Example
This example shows how to configure a simple PPP connection with CHAP authentication between two routers.

**Router A Configuration:**
RouterA(config)# interface Serial0/0/0
RouterA(config-if)# encapsulation ppp
RouterA(config-if)# ppp authentication chap
RouterA(config-if)# ppp chap hostname RouterA
RouterA(config-if)# ppp chap password cisco
RouterA(config-if)# ip address 10.1.1.1 255.255.255.252
RouterA(config-if)# no shutdown


**Router B Configuration:**
RouterB(config)# interface Serial0/0/0
RouterB(config-if)# encapsulation ppp
RouterB(config-if)# ppp authentication chap
RouterB(config-if)# ppp chap hostname RouterB
RouterB(config-if)# ppp chap password cisco
RouterB(config-if)# ip address 10.1.1.2 255.255.255.252
RouterB(config-if)# no shutdown


**Explanation:**
- `encapsulation ppp`: This command sets the data link layer protocol to PPP.
- `ppp authentication chap`: Enables CHAP authentication.
- `ppp chap hostname [hostname]`: The hostname that Router B will use to authenticate with Router A.
- `ppp chap password [password]`: The password that Router B must use to authenticate with Router A.

**Important Note:** The hostname and password on one router must match the corresponding values on the other router for a successful CHAP handshake.

**Verification Command:**
RouterA# show interfaces Serial0/0/0

This command will show if the line and protocol are up, and also the encapsulation type and authentication details.
