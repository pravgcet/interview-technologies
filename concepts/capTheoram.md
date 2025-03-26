# CAP Theorem

The **CAP Theorem** (also known as Brewer's Theorem) states that in a distributed data store, it is impossible to simultaneously guarantee all three of the following properties:

1. **Consistency (C):**

   - Every read receives the most recent write or an error.
   - Ensures that all nodes see the same data at the same time.

2. **Availability (A):**

   - Every request receives a (non-error) response, without guaranteeing the most recent write.
   - Ensures the system remains operational and serves requests even if some nodes are down.

3. **Partition Tolerance (P):**
   - The system continues to operate despite network partitions (communication breakdown between nodes).
   - Ensures the system works correctly even if messages between nodes are lost or delayed.

## Implication:

In the presence of a network partition, a distributed system must choose between **Consistency** and **Availability**:

- If **Consistency** is prioritized, the system will reject requests during the partition to ensure data integrity.
- If **Availability** is prioritized, the system will serve requests with potentially stale data.

## Examples:

- **CP Systems (Consistency + Partition Tolerance):**

  - Example: **HBase, Zookeeper**
  - Prioritizes consistency at the cost of availability during network partitions.

- **AP Systems (Availability + Partition Tolerance):**

  - Example: **Cassandra, DynamoDB**
  - Ensures availability but may serve stale data during network partitions.

- **CA Systems (Consistency + Availability):**
  - Not achievable in distributed systems if partitions are possible, as per the CAP Theorem.
