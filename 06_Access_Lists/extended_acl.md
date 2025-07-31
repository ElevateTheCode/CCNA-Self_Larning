# Extended Access Control Lists (ACLs)

## Extended ACLs
- **Criterion:** Extended ACLs provide more granular control by filtering traffic based on the **source IP**, **destination IP**, **protocol**, and **port number**.
- **Placement:** They should be placed as close to the **source** as possible to prevent unwanted traffic from crossing the network.
- **Syntax:** `access-list [acl_number] [permit|deny] [protocol] [source] [source_wildcard] [destination] [destination_wildcard] [operator port]`
- **Numbered:** `100-199` and `2000-2699`
- **Named:** `ip access-list extended [name]`

**Implicit Deny:** Just like standard ACLs, extended ACLs have an implicit `deny any any` at the end.

## Configuration Example
This example shows how to create an extended ACL to block web traffic (HTTP) from a specific subnet to a server.

**Scenario:**
- Block all HTTP traffic from the `192.168.1.0/24` network to the server at `10.1.1.5`.
- Allow all other traffic.
- Apply the ACL on the `GigabitEthernet0/0` interface, which is the source interface for the `192.168.1.0/24` network.

**Step 1: Create the ACL**
Router(config)# access-list 110 deny tcp 192.168.1.0 0.0.0.255 host 10.1.1.5 eq 80
Router(config)# access-list 110 permit ip any any

- `deny tcp ... eq 80`: This rule specifically denies TCP traffic with a destination port of 80 (HTTP).
- `permit ip any any`: This is a crucial line that permits all other traffic, overriding the implicit deny.

**Step 2: Apply the ACL to an interface**
Router(config)# interface GigabitEthernet0/0
Router(config-if)# ip access-group 110 in

- `ip access-group 110 in`: Applies ACL 110 to inbound traffic on this interface.

**Verification Command:**
Router# show access-lists 110

This command displays the rules for ACL 110 and shows how many packets have matched each rule.
