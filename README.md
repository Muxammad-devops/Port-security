🔐 Cisco Port Security – Packet Tracer Lab

This project demonstrates the implementation and validation of Switch Port Security in Cisco Packet Tracer. The objective is to prevent unauthorized devices from accessing the network by enforcing MAC-based access control at Layer 2.

🎯 Project Objectives

Restrict switch access ports to trusted devices only

Automatically block ports on unauthorized MAC address detection

Demonstrate real-world Layer 2 security behavior in a lab environment

🧠 Key Concepts Covered

switchport port-security configuration

Maximum allowed MAC addresses

Violation modes: protect, restrict, shutdown

Static vs Sticky MAC address learning

Verification and monitoring commands

⚙️ Sample Configuration (Cisco IOS)
enable
configure terminal

interface fastEthernet0/1
 switchport mode access
 switchport port-security
 switchport port-security maximum 1
 switchport port-security mac-address sticky
 switchport port-security violation shutdown
exit

do show port-security interface fastEthernet0/1

🧪 Test Scenario

Connect an authorized host → normal operation

Connect an unauthorized host → port transitions to err-disabled (shutdown)

Manual recovery:

interface fastEthernet0/1
 shutdown
 no shutdown
