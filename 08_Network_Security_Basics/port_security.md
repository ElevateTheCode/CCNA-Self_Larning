# Switch Port Security

## What is Port Security?
Port security is a Cisco switch feature that limits the number of MAC addresses that can be learned on a single switch port. This helps to prevent unauthorized devices from connecting to the network.

**How it works:**
- You can configure a port to allow only a specific number of MAC addresses.
- You can also configure the switch to learn a MAC address and stick with it.
- If an unauthorized device tries to connect, the switch will take a configured action.

## Configuration Example
This example shows how to configure a switch port to allow only one MAC address and a specific action if a violation occurs.

**Step 1: Set the port to access mode**
Switch(config)# interface FastEthernet0/1
Switch(config-if)# switchport mode access


**Step 2: Enable port security**
Switch(config-if)# switchport port-security


**Step 3: Configure the maximum number of MAC addresses**
Switch(config-if)# switchport port-security maximum 1


**Step 4: Configure the violation action**
- **shutdown:** The port is put into an error-disabled state. This is the default and most secure option.
- **restrict:** The port drops frames from the unauthorized device and increments a violation counter.
- **protect:** The port drops frames from the unauthorized device. No logging occurs.

Switch(config-if)# switchport port-security violation shutdown


**Step 5: Make the learned MAC address permanent (optional)**
Switch(config-if)# switchport port-security mac-address sticky


**Verification Command:**
Switch# show port-security
Switch# show port-security interface FastEthernet0/1

These commands display the port security settings and status.
