---
layout: default
title: etcd in Kubernetes
description: Distributed key-value store for cluster state
back: /kubernetes/basics.html
---

# 🧠 etcd in Kubernetes

`etcd` is a distributed, consistent key-value store used by Kubernetes to store all cluster data—configuration, state, secrets, and more.

## 🗂️ What etcd Stores

| Data Type        | Example                              |
|------------------|--------------------------------------|
| Cluster state    | Nodes, pods, deployments             |
| Configuration    | API server flags, admission policies |
| Secrets & config | TLS certs, ConfigMaps                |
| Events & leases  | Heartbeats, leader elections         |

## 🔐 Why etcd Matters

- **Consistency**: Uses Raft consensus algorithm  
- **Durability**: Writes are persisted to disk  
- **Availability**: Supports clustering and leader election  
- **Security**: TLS encryption and access control

## 🧠 Symbolic Metaphor

Imagine `etcd` as a **ledger in a secure vault**:
- Every Kubernetes action is a transaction
- The ledger records the current state
- Only trusted scribes (API server) can write to it
- The vault is replicated across trusted locations (nodes)

## 🔍 etcd in Action

- When you `kubectl apply`, the API server writes to `etcd`
- Controllers watch `etcd` for changes and act accordingly
- If `etcd` fails, Kubernetes loses its memory

## 🧪 Sample CLI Interaction

```bash
etcdctl get /registry/pods/default/web-app
