# Etcd

## What is Etcd?

Etcd is a distributed, reliable key-value store designed for storing configuration data, service discovery, and leader election in distributed systems. It is a core component of Kubernetes and other cloud-native systems.

## Key Features of etcd:

**1. Strong Consistency** – Uses the Raft consensus algorithm to ensure data consistency across all nodes.

**2. High Availability** – Replicated across multiple nodes for fault tolerance.

**3. Watch Mechanism** – Clients can subscribe to key changes for real-time updates.

**4. Simple API** – Uses gRPC and JSON over HTTP for easy integration.

**5. Secure** – Supports TLS encryption and authentication.

## How etcd Works in Kubernetes:
In Kubernetes, etcd stores all cluster configuration data, such as:

+ Node information
+ Pod details
+ Service discovery data
+ Role-based access control (RBAC) settings

If etcd fails, Kubernetes loses its ability to manage the cluster state. That’s why it’s often deployed in a highly available cluster with backups.


## How Is etcd Different from ZooKeeper?
|Feature|etcd|ZooKeeper
|---|---|---
|Consensus Algorithm|Raft|ZAB (ZooKeeper Atomic Broadcast)
Data Model|Simple key-value store|	Hierarchical (like a filesystem)
Performance|Faster reads/writes	|Slightly slower due to disk persistence
Kubernetes |Use	Core data store	|Used in older versions, but replaced by etcd
Complexity|Simple and lightweight|More complex with more features

### Basic etcd Operations
#### Write a Key-Value Pair:
```bash
etcdctl put mykey "Hello, etcd!"
```

#### Read the Key:
```bash
etcdctl get mykey
```
#### Delete a Key:
```bash
etcdctl del mykey
```

#### List All Keys:
```bash
etcdctl get "" --prefix
```

### Watching for Changes

etcd supports real-time updates using watch:

```bash
etcdctl watch mykey
```

Now, in another terminal, update mykey:

```bash
etcdctl put mykey "New Value!"
```

### Working with Directories (Prefixes)
#### Store hierarchical data:
```bash
etcdctl put /app/config/db "postgres"
etcdctl put /app/config/cache "redis"
```

#### Retrieve all keys under /app/config/:
```bash
etcdctl get /app/config/ --prefix
```

### Leader Election (For Distributed Systems)
```bash
etcdctl lease grant 10  # Create a lease for 10 seconds
etcdctl put leader "node1" --lease=<LEASE_ID>
etcdctl get leader
```
Once the lease expires, another node can take over.