---
layout: default
title: Kubernetes
description: Modular guide to Kubernetes architecture, components, and workflows
back: /index.md
---

# ☸️ Kubernetes Overview

Kubernetes is a **container orchestration platform**—a system that automates deployment, scaling, and management of containerized applications.

Think of it as a **digital city**:
- 🏙️ Nodes are buildings
- 📦 Pods are tenants
- 🧠 Control Plane is city hall
- 🚦 Scheduler is traffic control
- 🛠️ Controller Manager is maintenance crew
- 📚 ETCD is the city’s record keeper

---

## 🧭 Topics & Modules

Explore Kubernetes by component and function:

### 🧠 Control Plane

| Component             | Role                                                       |
|-----------------------|------------------------------------------------------------|
| [API Server](./kube-api-server.html)         | Front door to the cluster—handles all requests             |
| [Scheduler](./kube-scheduler.md)           | Assigns pods to nodes based on rules and availability      |
| [Controller Manager](./controller-manager.md) | Maintains desired state via controllers                  |
| [ETCD](./etcd.md)                          | Stores cluster state—key-value database                    |

---

### 🏗️ Node Components

| Component             | Role                                                       |
|-----------------------|------------------------------------------------------------|
| [Kubelet](./kubelet.md)                   | Talks to the API Server, runs containers on the node      |
| [Kube Proxy](./kube-proxy.md)             | Manages networking rules for service discovery            |
| [Container Runtime](./container-runtime.md) | Runs the actual containers (e.g., Docker, containerd)    |

---

### 🚀 Workloads & Scheduling

| Topic                  | Description                                               |
|------------------------|-----------------------------------------------------------|
| [Pods](./pods.md)                      | Smallest deployable unit—holds containers                  |
| [Deployments](./deployments.md)        | Declarative updates to pods and replicas                   |
| [Services](./services.md)              | Stable networking endpoint for pods                        |
| [Affinity & Taints](./scheduling-rules.md) | Custom scheduling behavior                              |

---

### 🔐 Security & Access

| Topic                  | Description                                               |
|------------------------|-----------------------------------------------------------|
| [RBAC](./rbac.md)                      | Role-based access control                                 |
| [Secrets](./secrets.md)                | Secure storage of sensitive data                          |
| [Network Policies](./network-policies.md) | Control traffic between pods                            |

---

## 🧩 Learning Flow

Start with the **Control Plane**, then explore **Node Components**, followed by **Workloads**, and finally **Security**.

> 🧠 Tip: Use symbolic diagrams and flashcards to reinforce each module. Try mapping the cluster like a city or a nervous system.

---

## 🔗 Related Sections

- [Docker](../docker/index.md)
- [Terraform](../terraform/index.md)
- [Azure](../azure/index.md)
