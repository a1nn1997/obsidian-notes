Technique used to horizontally partition data across multiple database instances or shards. 
Each shard contains a subset of the data, allowing for improved performance, scalability, and storage capacity. 
Sharding is commonly employed in scenarios where the data volume exceeds the capacity of a single database server or when high availability and fault tolerance are required. 

1. Range-based Sharding: 
	1. Range-based sharding involves dividing data based on a specific range of values. 
	2. For example, a database table could be partitioned based on a range of customer IDs or timestamps. 
	3. Each shard is responsible for a particular range, ensuring that data within that range is stored and processed within the corresponding shard. 
	4. Range-based sharding allows for efficient range-based queries but may face challenges when there are uneven data distributions or hotspots.
    
2. Hash-based Sharding: 
	1. Hash-based sharding distributes data across shards based on the result of applying a hash function to a specific attribute or a combination of attributes. 
	2. The hash function uniformly distributes data, ensuring a relatively even distribution across shards. 
	3. Hash-based sharding enables equal distribution of data, simplifies sharding logic, and provides good load balancing. 
	4. However, it can make range-based queries more complex, as the data is not sorted in a particular order across shards.
    
3. Directory-based Sharding: 
	1. Directory-based sharding uses a central directory or lookup service to map data to the appropriate shard. 
	2. The directory maintains a mapping between the data and its corresponding shard, allowing for efficient data routing and lookup. 
	3. This technique provides flexibility in terms of shard management, as it allows for dynamic addition or removal of shards without affecting the application logic. 
	4. Directory-based sharding requires an additional layer of indirection but provides improved scalability and shard management capabilities.
    
4. Composite Sharding: 
	1. Composite sharding combines multiple sharding techniques to create a more flexible partitioning scheme. 
	2. It involves using a combination of range-based and hash-based sharding, or other sharding techniques, to achieve a balance between data distribution, query optimization, and ease of management. 
	3. Composite sharding allows for a higher level of customization and control over the data distribution based on specific application requirements.
    
5. Consistent Hashing: 
	1. Consistent hashing is a technique used in distributed systems and sharding to minimize data redistribution when a shard is added or removed. 
	2. It provides a mapping between data and shards in a way that minimizes the number of data items that need to be reassigned when the number of shards changes. 
	3. Consistent hashing helps maintain data distribution and reduces the impact of adding or removing shards on the overall system.
    
6. Auto-sharding: 
	1. Auto-sharding refers to an automated mechanism that handles the distribution and management of data across shards. 
	2. It automatically determines how data is partitioned and routed to the appropriate shard based on predefined rules or algorithms. 
	3. Auto-sharding simplifies the management of sharding in dynamic environments where data volumes and access patterns change frequently.
    

