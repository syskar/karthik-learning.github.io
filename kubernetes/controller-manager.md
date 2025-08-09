---
layout: default
title: Kube Controller Manager
description: The orchestration brain behind Kubernetes automation
back: /kubernetes/control-plane.md
---

# 🧠 Kube Controller Manager

The **Kube Controller Manager** is the **automation brain** of Kubernetes. It runs a suite of controllers—each responsible for maintaining the desired state of different cluster components.

## 🧭 Symbolic Metaphor

Imagine Kubernetes as a **fleet of ships**:
- 🛳️ Each ship (node) carries containers (pods)
- 🏢 The Controller Manager is the **central office** that oversees departments:
  - 🚨 Node Office: Monitors ship health
  - 📦 Container Office: Ensures cargo (pods) are intact
  - 🧬 Replica Office: Maintains the right number of containers

Each department (controller) watches the fleet and takes action to restore order when something goes wrong.

---

## 🔧 What It Does

| Controller Type       | Role & Action                                                                 |
|------------------------|------------------------------------------------------------------------------|
| 🖥️ Node Controller     | Monitors node health; evicts pods from failed nodes                          |
| 🧬 Replication Controller | Ensures desired number of pod replicas are running                         |
| 📦 Deployment Controller | Manages rollout and scaling of deployments                                 |
| 🧠 Namespace Controller  | Handles lifecycle of namespaces                                              |
| 📁 PV Controller         | Manages persistent volume claims and bindings                               |

All these controllers run inside a **single process**: `kube-controller-manager`.

---

## ⚙️ Configuration & Location

| Setup Type        | How to View Options                                                              |
|-------------------|----------------------------------------------------------------------------------|
| `kubeadm`         | Pod manifest at `/etc/kubernetes/manifests/kube-controller-manager.yaml`        |
| Manual Setup      | Service file or process listing on master node                                   |

### 🔧 Common Flags

| Option                  | Purpose                                                                      |
|--------------------------|------------------------------------------------------------------------------|
| `--node-monitor-period` | Frequency of node health checks (default: 5s)                                |
| `--node-eviction-timeout` | Time before evicting pods from unreachable nodes (default: 5m)             |
| `--controllers`         | Specify which controllers to enable (default: all)                          |

---

## 📌 Key Takeaways

- The Controller Manager is a **single process** that runs multiple controllers.
- Each controller ensures a specific part of the cluster stays in its **desired state**.
- It interacts with the **API Server** to monitor and act on cluster changes.
- You can **customize behavior** using flags and selectively enable controllers.

---

## 🔗 Related Pages

- [Kube API Server](./kube-api-server.md)
- [Control Plane Overview](./control-plane.md)
- [ReplicaSets & Deployments](./../docker/replicas.md)
