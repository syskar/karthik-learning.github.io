---
layout: default
title: Azure Networking
description: Core concepts, services, and design patterns in Azure networking
back: /azure/index.html
---

# 🌐 Azure Networking

Azure networking forms the backbone of secure, scalable cloud architecture. Here's a breakdown of key components:

## 🔧 Core Services

| Service             | Purpose                                  | Notes                          |
|---------------------|-------------------------------------------|--------------------------------|
| Virtual Network (VNet) | Isolated network space for resources     | Like a private data center     |
| Subnets             | Logical segmentation within a VNet       | Enables tiered architecture    |
| Network Security Groups (NSGs) | Control inbound/outbound traffic | Acts like a firewall            |
| VPN Gateway         | Secure site-to-site or point-to-site VPN | Supports hybrid connectivity   |
| Azure Firewall      | Centralized traffic inspection           | Scales with cloud workloads    |

## 🧠 Design Patterns

- **Hub-and-Spoke**: Centralized hub VNet with spokes for workloads
- **Peering**: Connect VNets across regions or subscriptions
- **Bastion Host**: Secure RDP/SSH access without public IPs

## 📌 Visual Cue

Imagine your VNet as a city:
- Subnets are neighborhoods
- NSGs are security checkpoints
- VPN Gateway is the highway to other cities

## 🔗 Related Topics

- [Identity & Access](./identity.md)
- [Automation](./automation.md)
