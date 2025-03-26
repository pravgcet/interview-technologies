# Database Replication

**Database Replication** is the process of copying data from one database (the primary) to one or more databases (the replicas) to ensure redundancy, improve performance, and enhance data availability.

## Why Use Replication?

1. **High Availability:** Ensures continuous access to data even if the primary database fails.
2. **Load Balancing:** Distributes read requests across replicas to reduce the load on the primary database.
3. **Disaster Recovery:** Provides backup copies to recover from unexpected failures.
4. **Geographical Distribution:** Places replicas closer to users in different regions to reduce latency.

## Types of Replication:

1. **Master-Slave Replication:**

   - One primary (master) node handles all writes, and replicas (slaves) handle reads.
   - Example: MySQL Master-Slave setup.

2. **Master-Master Replication:**

   - Multiple masters handle both read and write requests.
   - Example: CouchDB allows multi-master replication.

3. **Snapshot Replication:**

   - Copies the entire dataset at regular intervals.
   - Suitable for low-change environments.

4. **Transactional Replication:**

   - Copies changes in near real-time, maintaining the order of transactions.
   - Ideal for systems requiring high consistency.

5. **Logical Replication:**
   - Replicates specific data changes (like inserts, updates, and deletes) based on a logic layer.
   - Example: PostgreSQL Logical Replication.

## Advantages of Replication:

- Improves data availability and fault tolerance.
- Enhances performance by balancing read-heavy workloads.
- Supports disaster recovery.

## Disadvantages of Replication:

- Increases storage and operational complexity.
- May lead to data inconsistency if not properly managed.
- Adds latency due to replication lag.

Types:

Synchronous: Safer, but slower (waits for confirmation).
Asynchronous: Faster, but at risk of data loss during failure.
