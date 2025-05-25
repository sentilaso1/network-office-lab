# Network VLAN Project with Router-on-a-Stick

This project is a Packet Tracer simulation of a segmented network using VLANs and inter-VLAN routing via a Router-on-a-Stick model. It includes DHCP, DNS, and ACL configurations for a realistic enterprise setup.

---

## 📌 Features

✅ VLAN segmentation (HR, IT, Guest)  
✅ Inter-VLAN Routing using Router 2901  
✅ DHCP Server (on Router) for IP auto-assignment  
✅ DNS Server (internal) with domain name resolution  
✅ ACL to restrict access from Guest VLAN to HR VLAN  

---

## 🧱 Network Topology

- **Switch 3650** with VLANs 10 (HR), 20 (IT), 30 (Guest)
- **Router 2901** configured with sub-interfaces (dot1Q)
- **Internal Server**: Provides DNS service and (optionally) hosts a local website
- **Clients (PCs)**: Assigned dynamically via DHCP

📷 _See_ `/screenshots/` for Packet Tracer diagram and test results

**Note**: Switch ports in Packet Tracer may be labeled as `FastEthernet` or `GigabitEthernet` depending on the model. This project uses `GigabitEthernet` for Cisco 3650 compatibility.

---

## 🖧 IP Addressing Scheme

| VLAN  | Subnet             | Gateway          | Role     |
|-------|--------------------|------------------|----------|
| HR    | 192.168.10.0/24    | 192.168.10.1     | Staff    |
| IT    | 192.168.20.0/24    | 192.168.20.1     | Admin    |
| Guest | 192.168.30.0/24    | 192.168.30.1     | Visitors |

---

## 🔐 ACL Policy

- ACL 100: Deny access from VLAN 30 (Guest) to VLAN 10 (HR)
```bash
access-list 100 deny ip 192.168.30.0 0.0.0.255 192.168.10.0 0.0.0.255
access-list 100 permit ip any any
```

---

## 🧪 How to Test

1. Open `packet-tracer.pkt` in Cisco Packet Tracer
2. Power on all devices
3. Check IP assigned via DHCP
4. Try `ping intranet.local` from PC (DNS resolution)
5. Try pinging from Guest VLAN to HR VLAN (should fail)
6. (Optional) Access intranet.local in a PC's web browser if HTTP is enabled on the server
---

## 📁 Project Structure

```
network-vlan-router/
├── config-commands.txt     # Full CLI configuration
├── packet-tracer.pkt       # Packet Tracer simulation
├── README.md               # Project overview
├── report.pdf              # Report document
└── screenshots/            # Captures of successful tests
```
---

## 🚀 Future Improvements

To enhance this network setup in future iterations, consider the following developments:

- **Add VLAN Security**: Implement `port-security` on switch ports to restrict MAC addresses, preventing unauthorized devices from connecting.
- **DHCP Snooping**: Enable `ip dhcp snooping` to protect against rogue DHCP servers, especially for the Guest VLAN.
- **Multiple Routers**: Introduce a second router for redundancy using protocols like HSRP or VRRP.
- **External Connectivity**: Add a WAN link to simulate internet access, with NAT/PAT configuration on the router.
- **Advanced ACLs**: Expand ACLs to include time-based restrictions or additional policies (e.g., block Guest VLAN from IT VLAN).
- **Monitoring**: Integrate SNMP or syslog for network monitoring and logging.
- **IPv6 Support**: Add IPv6 addressing and routing to support modern network requirements.
- **Wireless Access**: Include a wireless access point for Guest VLAN to simulate a realistic guest network.
- **Server Enhancements**: Configure a more robust web server (e.g., custom HTML page for `intranet.local`) or add additional services like FTP or email.

---

## ✅ Requirements

- Cisco Packet Tracer (7.x or higher)
- Basic understanding of VLANs, IP routing, DHCP, and ACLs

---

## 👨‍💻 Author

Made with ❤️ by senti
