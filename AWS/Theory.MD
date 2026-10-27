# AWS Networking Notes

## Network

- Network = Devices communicating with each other.
- Internet = Network of Networks.
- Every device needs an IP address.

---

## IP Address

- IPv4 = 32-bit address.
- Unique identifier of a device.
- Used for routing packets.

Example:
```
192.168.1.10
```

---

## Public IP

- Globally unique.
- Internet reachable.
- Assigned by ISP/Cloud Provider.

Example:
```
13.x.x.x
```

---

## Private IP

- Used inside private networks.
- Not routable over the Internet.

Ranges:
```
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
```

---

## Router

- Connects different networks.
- Decides where packets should go.

---

## NAT

- Converts Private IP ↔ Public IP.
- Many devices can share one Public IP.
- Uses Port Mapping.

---

## Ports

- Identify applications on a machine.

Common Ports:

| Port | Service |
|------|---------|
| 22 | SSH |
| 80 | HTTP |
| 443 | HTTPS |
| 5432 | PostgreSQL |
| 6379 | Redis |

---

## VPC

- Private virtual network inside AWS.
- Own isolated IP space.
- Everything lives inside a VPC.

Example:
```
10.0.0.0/16
```

---

## CIDR

- Defines network size.
- /16 = 16 Network Bits.
- Remaining bits = Host Bits.

Formula:
```
Hosts = 2^(32-prefix)
```

Examples:

| CIDR | Total IPs |
|------|----------:|
| /24 | 256 |
| /16 | 65536 |

---

## Subnet

- Logical partition of a VPC.
- Used for organization and security.

Example:
```
VPC
10.0.0.0/16

├── Public
10.0.1.0/24

└── Private
10.0.2.0/24
```

---

## Route Table

- Decides where packets go.

Rules:
```
10.0.0.0/16 -> Local

0.0.0.0/0 -> Internet Gateway
```

---

## Internet Gateway (IGW)

- Connects VPC to the Internet.
- Attached to a VPC.
- Does NOT assign Public IPs.

---

## NAT Gateway

- AWS Managed NAT.
- Lives in Public Subnet.
- Allows Private resources to access Internet.
- Blocks unsolicited inbound traffic.

Flow:
```
Private EC2

↓

NAT Gateway

↓

Internet Gateway

↓

Internet
```

---

## Security Group

- Resource-level firewall.
- Stateful.
- Allow rules only.
- Attached to EC2, ALB, RDS etc.

Best Practice:

```
Internet

↓

ALB SG

↓

EC2 SG

↓

RDS SG
```

Never expose DB to:
```
0.0.0.0/0
```

---

## NACL

- Subnet-level firewall.
- Stateless.
- Allow + Deny.
- Rule order matters.

---

## Stateful vs Stateless

Security Group
```
Request Allowed

↓

Reply Automatically Allowed
```

NACL
```
Inbound Rule

+

Outbound Rule

Both Required
```

---

# Complete Packet Flow

```
Browser

↓

Internet

↓

Internet Gateway

↓

ALB

↓

EC2

↓

RDS

↓

Response
```

External API Call

```
EC2

↓

NAT Gateway

↓

Internet Gateway

↓

Internet
```

---

# Quick Revision

| Component | Purpose |
|-----------|---------|
| VPC | Private Network |
| CIDR | IP Range |
| Subnet | Network Partition |
| Route Table | Packet Routing |
| Internet Gateway | Internet Access |
| NAT Gateway | Private → Internet |
| Security Group | Resource Firewall |
| NACL | Subnet Firewall |