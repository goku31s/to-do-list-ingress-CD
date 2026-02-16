# 3-Tier App: Ingress CD (Advanced Networking)

This repository contains the Kubernetes manifests required to deploy the application using a **GKE Ingress Controller** instead of a standard LoadBalancer Service.

## 🛰️ Networking Architecture
- **Ingress:** Manages path-based routing for the application.
- **Service (NodePort):** The Webapp service is downgraded to `NodePort` (as required by GKE Ingress) to keep the backend internal.
- **Routing Rules:**
    - Path `/` -> `webapp-service:80`
    - Path `/page1` -> `webapp-service:80`
    - Path `/page2` -> `webapp-service:80`

## 🛠️ Requirements
- Requires a GKE Cluster with the HTTP Load Balancing add-on enabled.
