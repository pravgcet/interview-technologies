# Kubernetes

Kubernetes (often abbreviated as K8s) is an open-source container orchestration platform that helps automate the deployment, scaling, and management of containerized applications. It was originally developed by Google and is now maintained by the Cloud Native Computing Foundation (CNCF).

## Key Features of Kubernetes:

**1. Container Orchestration** – Manages containers (Docker or others) across multiple hosts.

**2. Scaling & Load Balancing** – Automatically scales applications up or down and distributes traffic efficiently.

**3. Self-Healing** – Restarts failed containers and replaces unresponsive ones.

**4. Service Discovery** – Provides built-in networking to help containers communicate.

**5. Automated Deployments & Rollbacks** – Ensures smooth software releases with minimal downtime.

**6. Storage Orchestration** – Manages persistent storage (e.g., cloud volumes, local storage).

## Why Use Kubernetes?

- Handles complex deployments with microservices.
- Improves resource utilization and efficiency.
- Works across different cloud providers or on-premise.
- Enables CI/CD (Continuous Integration/Continuous Deployment) workflows.

## Kubernetes Architecture & Structure

Kubernetes follows a Master-Worker architecture, where the Control Plane (Master Node) manages the Worker Nodes that run the application workloads.

### 1️. Control Plane (Master Node)

The Control Plane is responsible for managing the entire Kubernetes cluster, making decisions on deployments, scaling, and scheduling.

🔹 Key Components of the Control Plane:

- **API Server (kube-apiserver)** – The front-end of Kubernetes, handling all requests from users, CLI (kubectl), and other components.

- **Controller Manager (kube-controller-manager)** – Ensures the desired state of the cluster (e.g., maintains replica counts, node health, etc.).

- **Scheduler (kube-scheduler)** – Assigns workloads (Pods) to Worker Nodes based on resource availability.

- **etcd (Key-Value Store)** – A distributed database that stores the entire cluster state and configuration.

- **Cloud Controller Manager (optional)** – Integrates with cloud providers (AWS, GCP, Azure) for resources like load balancers and storage.

### 2. Worker Nodes

Worker Nodes actually run the containerized applications. Each node has the necessary services to manage and execute Pods.

🔹 Key Components of a Worker Node:

- **Kubelet** – An agent running on each node, responsible for communication with the Control Plane and managing containers.

- **Container Runtime (Docker, containerd, CRI-O, etc.)** – Runs and manages the actual containers.

- **Kube Proxy** – Manages networking and load balancing between Pods inside the cluster.

### 3. Kubernetes Objects

These are the building blocks of applications in Kubernetes.

- **Pods** – The smallest unit in Kubernetes, which contains one or more containers.

- **Deployments** – Manages rolling updates and scaling of Pods.

- **Services** – Exposes applications running in Pods to internal or external traffic.

- **ConfigMaps & Secrets** – Store configuration data securely.

- **Persistent Volumes (PVs) & Persistent Volume Claims (PVCs)** – Handle storage for applications.

### 4. Kubernetes Networking

- **ClusterIP** – Internal communication within the cluster.

- **NodePort** – Exposes services on a specific port of a node.

- **LoadBalancer** – Exposes services to the internet.

- **Ingress** – Routes external traffic to specific services.

### How This Fits Into CI/CD?

The deployment process typically looks like this:

**1. Code Commit** → Triggers CI pipeline (builds a Docker image).

**2. Push to Registry** → Image is stored in Docker Hub, AWS ECR, or another registry.

**3. CD Pipeline (Harness)** → Deploys the new image to Kubernetes.

**4. Kubernetes Scheduler** → Schedules the application in Worker Nodes.

**5. Services & Ingress** → Exposes the application for users.

## What is a Node?

A Node is a worker machine in a Kubernetes cluster that runs application workloads. It can be a physical server or a virtual machine (VM).

Each Node contains:

- **Kubelet** – Communicates with the control plane & manages containers.
- **Container Runtime** – Runs containers (e.g., Docker, containerd).
- **Kube Proxy** – Manages networking & load balancing between Pods.

🔹 Types of Nodes:

- **Master Node (Control Plane)** – Manages the cluster & scheduling.
- **Worker Node** – Runs the actual applications (Pods).

## What is a Pod?

A Pod is the smallest deployable unit in Kubernetes. It represents a single instance of a running process in your cluster.

A Pod contains:

- One or more containers (usually Docker).
- Networking – Each Pod gets a unique IP address.
- Storage (optional) – Can attach Persistent Volumes.

🔹 Types of Pods:

- **Single-Container Pod** – Runs one container (most common).
- **Multi-Container Pod** – Runs multiple tightly coupled containers (e.g., app + logging agent).
