# Kubernetes Zero to Hero Guide

## Overview

This repository is a comprehensive resource for learning Kubernetes from scratch, progressing from basic concepts to advanced deployments and real-world use cases. Handwritten notes, YAML files, and practical examples are included to solidify learning.

---

### Key Topics Covered

#### 1. **Introduction to Kubernetes**
- What is Kubernetes? Why use it?
- Kubernetes architecture and components
  - Master Node: API Server, etcd, Controller Manager, Scheduler
  - Worker Node: Kubelet, Kube Proxy, Container Runtime

#### 2. **Kubernetes Objects**
- **Pods**: The smallest deployable unit
- **ReplicaSets**: Ensures desired number of pods
- **Deployments**: Manages ReplicaSets and updates
- **Services**: Networking for Pods (ClusterIP, NodePort, LoadBalancer)
- **ConfigMaps**: Injecting configuration data
- **Secrets**: Storing sensitive information
- **Persistent Volumes (PV) and Persistent Volume Claims (PVC)**: Managing storage

#### 3. **YAML Manifest Files**
- Writing Kubernetes YAML files for Pods, Deployments, and Services
- Understanding `apiVersion`, `kind`, `metadata`, `spec`

#### 4. **Cluster Networking**
- Service discovery with DNS
- Networking models (Flat network, CNI plugins)
- Ingress resources and controllers

#### 5. **Scaling Applications**
- Horizontal Pod Autoscaler (HPA)
- Vertical Pod Autoscaler (VPA)

#### 6. **Storage in Kubernetes**
- Volumes, Persistent Volumes (PV), Persistent Volume Claims (PVC)
- Dynamic provisioning with StorageClasses

#### 7. **Advanced Kubernetes**
- Rolling Updates and Rollbacks
- Blue-Green Deployments
- Canary Deployments

#### 8. **Kubernetes Security**
- Role-Based Access Control (RBAC)
- Network policies
- Pod security policies

#### 9. **Monitoring and Logging**
- Tools: Prometheus, Grafana
- Logging with Fluentd and Elasticsearch

#### 10. **Helm**
- Introduction to Helm
- Writing Helm charts
- Using Helm for application deployment

#### 11. **Kubernetes in Production**
- Best practices for managing clusters
- Disaster recovery strategies
- Upgrading Kubernetes clusters

---

### Prerequisites

- Basic understanding of Docker and containerization
- Familiarity with YAML syntax
- Access to a Kubernetes cluster (local or cloud)
  - Use [Minikube](https://minikube.sigs.k8s.io/docs/start/) for local setup
  - Use managed Kubernetes services like EKS, GKE, or AKS for cloud

---

### Getting Started

1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd kubernetes-zero-to-hero
   ```

2. **Install Required Tools**:
   - [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/): CLI to interact with Kubernetes
   - [Minikube](https://minikube.sigs.k8s.io/docs/start/): Local Kubernetes cluster setup

3. **Follow Handwritten Notes and Examples**:
   - Notes are available in the `notes/` directory
   - YAML examples are in the `manifests/` directory

---

### Example: Creating a Pod

#### YAML File: `nginx-pod.yaml`
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  labels:
    app: nginx
spec:
  containers:
  - name: nginx
    image: nginx:latest
    ports:
    - containerPort: 80
```

#### Commands:
```bash
# Apply the manifest
kubectl apply -f nginx-pod.yaml

# Check the Pod status
kubectl get pods

# Access the logs
kubectl logs nginx-pod
```

---

### Contributions

Contributions are welcome! Submit issues or pull requests to enhance the repository or add new examples.

---

### License

This guide is open-source and available under the [MIT License](LICENSE).
