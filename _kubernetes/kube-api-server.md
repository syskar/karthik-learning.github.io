---
layout: default
title: Kubernetes API Server
description: Central gateway and coordinator for all Kubernetes operations
back: /kubernetes/control-plane.md
---

# 🗣️ Kubernetes API Server (`kube-apiserver`)

The **kube-apiserver** is the **central gateway** to your Kubernetes cluster. It exposes the Kubernetes API and acts as the interface between users, components, and the cluster state.

## 🔧 What It Does

| Function            | Description                                           |
|---------------------|-------------------------------------------------------|
| API Gateway         | Accepts REST requests via `kubectl`, clients, etc.    |
| Authentication      | Verifies identity of users and components             |
| Authorization       | Enforces RBAC policies                                |
| Admission Control   | Validates and mutates incoming requests               |
| State Management    | Reads/writes cluster state to `etcd`                  |
| Watch Mechanism     | Notifies controllers of changes in cluster state      |

## 🧠 Symbolic Metaphor

Imagine the API Server as the **reception desk** of a high-security facility:
- 🗣️ Visitors (users, controllers) submit requests
- 🧾 The receptionist checks ID (authentication)
- ✅ Verifies permissions (authorization)
- 🧮 Logs the request in the central ledger (etcd)
- 📢 Notifies departments (controllers) to act

---

## 📌 Key Points to Remember

### ✅ Must-Know Facts

- It’s the **only component** that talks directly to `etcd`
- All `kubectl` commands go through the API server
- Controllers and schedulers **watch** the API server for changes
- It’s stateless—can be scaled horizontally
- Runs on port `6443` by default

### ⚠️ Operational Tips

| Tip                          | Description                                      |
|------------------------------|--------------------------------------------------|
| 🔐 Secure with TLS          | Encrypt all API traffic                          |
| 🔍 Audit Logs               | Enable logging for compliance and debugging      |
| 🧱 Use RBAC                 | Enforce fine-grained access control              |
| 🧪 Health Checks            | Monitor with `/healthz` and `/livez` endpoints   |
| 🚫 Don’t expose publicly    | Restrict access via firewall or VPN              |

---

## 🔗 Related Pages

- [ETCD Role](./etcd-role.html)
- [Control Plane Overview](./control-plane.md)
- [RBAC & Identity](./../azure/identity.html)
