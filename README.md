# 🪁 Kite — Modern Kubernetes Dashboard

**A lightweight, modern Kubernetes management platform for multi-cluster operations, observability, resource management, security, and AI-assisted workflows.**

Kite provides a unified web interface for managing Kubernetes infrastructure without relying entirely on `kubectl`. It combines cluster administration, live resource monitoring, YAML editing, logs, terminals, Helm management, access control, and AI-assisted operations in a single workspace.

## ✨ Key Capabilities

* **Multi-Cluster Management** — Connect and switch between multiple Kubernetes clusters.
* **Resource Management** — Manage Pods, Deployments, Services, ConfigMaps, Secrets, Nodes, PVs, PVCs, CRDs, and more.
* **Live YAML Editor** — Inspect and modify Kubernetes resources using a Monaco-based editor.
* **Observability** — Monitor CPU, memory, network, events, and Prometheus metrics.
* **Pod Logs** — Stream and search live container logs.
* **Web Terminal** — Execute commands directly inside pods and nodes.
* **Helm Management** — Discover, install, upgrade, rollback, and manage Helm releases.
* **AI Assistant** — Interact with Kubernetes environments through AI-assisted workflows.
* **Kube Proxy** — Access pods and services without manually configuring `kubectl port-forward`.
* **Security & Governance** — OAuth, MFA, passkeys, RBAC, user management, and audit capabilities.
* **Responsive UI** — Desktop, tablet, and mobile-friendly interface with theme support.
* **Internationalization** — English and Chinese language support.

## 🏗️ Architecture

```text
                    ┌─────────────────────┐
                    │      Web UI         │
                    │  React / TypeScript │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Kite API Server   │
                    │        Go           │
                    └──────────┬──────────┘
                               │
              ┌────────────────┼────────────────┐
              │                │                │
              ▼                ▼                ▼
       ┌────────────┐   ┌────────────┐   ┌────────────┐
       │ Kubernetes │   │ Prometheus │   │   Storage  │
       │   API      │   │  Metrics   │   │ / Database │
       └────────────┘   └────────────┘   └────────────┘
              │
              ▼
       ┌────────────────┐
       │ Cluster / Pods  │
       │ Services / CRDs │
       └────────────────┘
```

## 🛠️ Technology Stack

### Backend

* Go
* Kubernetes API
* REST APIs
* Kubernetes client libraries
* Prometheus integration

### Frontend

* TypeScript
* React
* Modern component-based UI
* Monaco Editor
* Responsive dashboard architecture

### Infrastructure

* Kubernetes
* Docker
* Helm
* Docker Compose
* OCI container images
* Prometheus

### Security

* OAuth
* MFA
* Passkeys
* RBAC
* User and role management
* Audit logging

### AI

* AI-assisted Kubernetes operations
* AI assistant workflows
* Agent/tool integration
* Kubernetes-aware context

## 🚀 Running with Docker

```bash
docker run -d \
  -p 8080:8080 \
  -v ./data:/data \
  -e DB_DSN=/data/db.sqlite \
  ghcr.io/kite-org/kite:latest
```

Open:

```text
http://localhost:8080
```

## ☸️ Kubernetes Deployment

Using Helm:

```bash
helm install kite \
  oci://ghcr.io/kite-org/charts/kite \
  -n kube-system
```

Or:

```bash
helm repo add kite https://kite-org.github.io/kite/
helm repo update
helm install kite kite/kite -n kube-system
```

Access through port forwarding:

```bash
kubectl port-forward \
  -n kube-system \
  svc/kite \
  8080:8080
```

## 💻 Development

```bash
git clone https://github.com/kite-org/kite.git
cd kite

make deps
make build
make run
```

## 🔧 Engineering Areas

This project is particularly interesting from an engineering perspective because it brings together several production infrastructure concerns:

* Kubernetes API integration
* Multi-cluster resource abstraction
* Real-time infrastructure observability
* Secure administrative workflows
* RBAC and authentication
* YAML-based infrastructure management
* Helm lifecycle automation
* Container and pod operations
* Prometheus metrics
* AI-assisted infrastructure management
* Responsive frontend architecture
* Self-hosted deployment

## 🎯 Why Kite?

Traditional Kubernetes workflows often require switching between dashboards, terminals, monitoring systems, and deployment tools.

Kite brings these workflows together into a single operational interface:

```text
Cluster
   │
   ├── Resources
   ├── Workloads
   ├── Logs
   ├── Metrics
   ├── Events
   ├── Terminal
   ├── YAML
   ├── Helm
   ├── Security
   └── AI Assistant
```

## 📌 Project Focus

**Cloud Native · Kubernetes · Go · TypeScript · React · DevOps · Observability · RBAC · Helm · AI Agents**

## 📄 License

Apache License 2.0.
