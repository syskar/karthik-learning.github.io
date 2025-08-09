---
layout: default
title: Kubernetes Scheduler
description: How Kubernetes decides where to run pods
back: /kubernetes/control-plane.md
---

# 🫀 Kubernetes Scheduler (`kube-scheduler`)

The **kube-scheduler** is the **decision-making engine** of Kubernetes. It assigns newly created pods to suitable nodes based on resource availability, constraints, and policies.

## 🧠 Symbolic Metaphor

Think of the scheduler as the **heart of a logistics system**:
- 🧾 Pods are packages waiting to be shipped
- 🏗️ Nodes are warehouses with varying capacity
- 🫀 The scheduler decides which warehouse gets which package—based on space, location, and rules

---

## 🔧 What It Does

| Step                | Description                                                                 |
|---------------------|------------------------------------------------------------------------------|
| Detects Unscheduled Pods | Watches API Server for pods without assigned nodes                      |
| Evaluates Nodes     | Filters out nodes that don’t meet pod requirements                          |
| Scores Candidates   | Ranks remaining nodes based on priority functions                           |
| Assigns Pod         | Updates pod spec with selected node name via API Server                     |

---

## 🧪 Scheduling Criteria

| Filter / Rule         | Purpose                                               |
|------------------------|-------------------------------------------------------|
| Resource Requests      | CPU, memory, ephemeral storage                        |
| Node Affinity / Taints | Match pods to preferred or restricted nodes          |
| Pod Affinity / Anti-Affinity | Co-locate or separate pods based on labels     |
| Constraints            | Zone, region, custom labels                          |

---

## ⚙️ Configuration & Location

| Setup Type        | How to View Options                                                              |
|-------------------|----------------------------------------------------------------------------------|
| `kubeadm`         | Pod manifest at `/etc/kubernetes/manifests/kube-scheduler.yaml`                 |
| Manual Setup      | Service file or process listing on master node                                   |

### 🔧 Common Flags

| Option                  | Purpose                                                                      |
|--------------------------|------------------------------------------------------------------------------|
| `--policy-config-file`  | Custom scheduling rules                                                      |
| `--leader-elect`        | Enables high availability mode                                               |
| `--profiling`           | Enables performance profiling                                                |

---

## 📌 Key Takeaways

- The scheduler assigns pods to nodes based on **filters and scoring**
- It does **not** create pods—just decides where they go
- It interacts with the **API Server**, not directly with nodes
- You can customize scheduling behavior with **affinity rules**, **taints**, and **priorities**

---

## 🔗 Related Pages

- [Kube Controller Manager](./controller-manager.md)
- [Kube API Server](./kube-api-server.md)
- [Control Plane Overview](./control-plane.md)
