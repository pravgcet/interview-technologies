# Sharding

**Sharding** is a database architecture pattern that involves splitting a large dataset into smaller, more manageable pieces called _shards_, which are distributed across multiple database servers. Each shard is an independent database containing a subset of the overall data.

## Advantages of Sharding:

1. **Scalability:**
   - Enables horizontal scaling by adding more servers to handle growing data.
2. **Improved Performance:**
   - Reduces query load on each server, leading to faster response times.
3. **Increased Availability:**
   - Even if one shard fails, the rest of the system remains operational.
4. **Cost Efficiency:**
   - Allows the use of cheaper, commodity hardware for each shard.

## Disadvantages of Sharding:

1. **Complexity:**
   - Adds operational complexity in managing multiple shards.
2. **Data Distribution Challenges:**
   - Uneven distribution can lead to "hot spots" where some shards handle more traffic than others.
3. **Rebalancing Issues:**
   - Difficult to redistribute data when adding new shards.
4. **Cross-shard Queries:**
   - Queries involving multiple shards can become complex and slower.

## Types of Sharding:

1. **Range-based Sharding:**
   - Data is divided based on a range of values.
   - Example: User IDs 1-1000 go to Shard A, 1001-2000 go to Shard B.
2. **Hash-based Sharding:**
   - Uses a hash function to assign data to shards.
   - Ensures even distribution but makes range queries harder.
3. **Geographic Sharding:**
   - Data is partitioned based on geographic regions.
   - Example: US data goes to Shard A, EU data to Shard B.
4. **Directory-based Sharding:**
   - Uses a lookup service to determine the appropriate shard for each piece of data.
   - Offers flexibility but adds a dependency on the directory service.
