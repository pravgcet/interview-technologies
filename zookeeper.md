# Zookeeper

## What is Apache zookeeper?

Apache ZooKeeper is a distributed coordination service that helps manage large-scale distributed systems. It provides essential services like:

**1. Configuration management** – Keeps system configurations consistent across nodes.

**2. Leader election** – Helps distributed applications select a leader dynamically.

**3. Synchronization** – Prevents race conditions in distributed environments.

**4. Naming registry** – Acts as a hierarchical namespace for nodes (similar to a filesystem).

**5. Distributed locks** – Ensures that only one process can access a shared resource at a time.

## How It Works?

ZooKeeper maintains a hierarchical structure (like a filesystem) where data is stored in nodes called znodes. It follows a replicated consensus protocol to ensure reliability, meaning multiple ZooKeeper servers run in a cluster, and a majority must agree on any changes.

## Give some use-cases

- Managing Kafka brokers
- Coordinating Hadoop clusters
- Service discovery in microservices
- Distributed lock management
