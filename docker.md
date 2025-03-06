# Docker

## What is Docker? 🐳

Docker is an open-source containerization platform that allows you to package applications and their dependencies into containers. Containers ensure that an application runs consistently across different environments (development, testing, production).

## Why Use Docker?

- **Portability** – Run anywhere (local machine, cloud, Kubernetes, etc.).
- **Lightweight** – Shares the host OS, unlike VMs, making it more efficient.
- **Scalability** – Easily scale applications by running multiple container instances.
- **Fast Deployment** – Launch applications in seconds.
- **Dependency Management** – Bundles all required libraries, configs, and dependencies.

## How Docker Works

**1. Dockerfile** – A script that defines how to build a container image.

**2. Image** – A read-only template containing application code, dependencies, and OS libraries.

**3. Container** – A running instance of an image.

**4. Docker Hub/Registry** – A storage for Docker images (public or private).

**5. Docker Engine** – The runtime that executes and manages containers.

## Docker vs Virtual Machines (VMs)

| Feature        | Docker (Containers) | Virtual Machines (VMs)       |
| -------------- | ------------------- | ---------------------------- |
| Speed          | Fast (seconds)      | Slow (minutes)               |
| Size           | Lightweight (MBs)   | Heavy (GBs)                  |
| Resource Usage | Shares OS Kernel    | Requires full OS             |
| Portability    | High                | Lower due to OS dependencies |

## Docker & Kubernetes

Docker provides containers, while Kubernetes manages them at scale.

1. Docker builds & runs containers (docker run myapp).
2. Kubernetes orchestrates multiple Docker containers (kubectl apply -f deployment.yaml).
