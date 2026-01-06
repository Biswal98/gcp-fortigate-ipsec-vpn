# gcp-fortigate-ipsec-vpn
Site-to-Site IPsec VPN between GCP and FortiGate Firewall

# GCP ↔ FortiGate Site-to-Site IPsec VPN

This repository documents the design and configuration of a Site-to-Site IPsec VPN tunnel between Google Cloud Platform (GCP) and a FortiGate firewall.  
The objective is to establish secure, encrypted connectivity between an on-premises network and a GCP VPC.

---

## Architecture Overview

The solution uses GCP Cloud VPN to securely connect an on-premises network protected by a FortiGate firewall.  
Traffic between both environments is encrypted using IPsec and routed either via static routes or BGP.

---

## Architecture Diagram

![GCP FortiGate IPsec VPN](architecture/gcp-fortigate-vpn-diagram.png)

---

## Technologies Used

- Google Cloud Platform (GCP)
  - VPC
  - Cloud VPN
  - Cloud Router
- FortiGate Firewall
- IPsec VPN (IKEv2)
- BGP / Static Routing

---

## Prerequisites

- Active GCP project
- Existing VPC and subnet in GCP
- FortiGate firewall with internet connectivity
- Public IP address configured on FortiGate WAN interface
- Administrative access to GCP Console and FortiGate
- Basic understanding of IPsec and routing concepts

---

## VPN Design Parameters

- VPN Type: Site-to-Site IPsec
- IKE Version: IKEv2
- Authentication: Pre-Shared Key
- Encryption: AES-256
- Integrity: SHA-256
- Diffie-Hellman Group: 14
- Routing: BGP or Static

---

## Network Information (Example)

| Component | Value |
|---------|------|
| GCP VPC CIDR | `<GCP_VPC_CIDR>` |
| On-Prem Network CIDR | `<ON_PREM_CIDR>` |
| GCP VPN Gateway IP | `<GCP_VPN_PUBLIC_IP>` |
| FortiGate WAN IP | `<FORTIGATE_PUBLIC_IP>` |

> **Note:** All values are placeholders. Do not expose real IP addresses or secrets.

---

## High-Level Configuration Flow

1. Create VPC and subnet in GCP
2. Configure Cloud VPN gateway in GCP
3. Configure Cloud Router and BGP (if required)
4. Configure IPsec Phase 1 and Phase 2 on FortiGate
5. Create firewall policies and routing on FortiGate
6. Verify VPN tunnel and test traffic flow

---

## Verification and Testing

- Verify VPN tunnel status in GCP Console
- Check IPsec tunnel status on FortiGate
- Ping between on-prem and GCP instances
- Verify routing table and BGP session (if applicable)

---

## Common Issues and Troubleshooting

- Phase 1 or Phase 2 proposal mismatch
- Incorrect local or remote subnets
- Firewall policy missing on FortiGate
- NAT not excluded for VPN traffic
- BGP session not establishing

Detailed troubleshooting steps are available in the `troubleshooting/` directory.

---

## Security Best Practices

- Use strong encryption and hashing algorithms
- Rotate pre-shared keys periodically
- Limit firewall rules to required subnets only
- Enable logging and monitoring on both sides
- Use HA VPN for production environments

---

## Repository Structure



---

## Disclaimer

This repository is intended for learning and reference purposes only.  
Always validate configurations and follow security best practices before using in production environments.

---

## Author

Smruti  
Cloud & Network Security Engineer
