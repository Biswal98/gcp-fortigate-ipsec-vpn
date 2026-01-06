# FortiGate IPsec Configuration

## Phase 1
- IKE version: IKEv2
- Remote Gateway: <GCP_VPN_PUBLIC_IP>
- Encryption: AES-256
- DH Group: 14

## Phase 2
- Local Subnet: <ON_PREM_SUBNET>
- Remote Subnet: <GCP_SUBNET>
- PFS: Enabled

## Firewall Policy
- Allow LAN to VPN
- Allow VPN to LAN
- Disable NAT for VPN traffic
