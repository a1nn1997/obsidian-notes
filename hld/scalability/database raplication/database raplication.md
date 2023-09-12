Technique that involves creating and maintaining multiple copies of a database across different servers or locations. 
Replication enhances data availability, reliability, and performance by ensuring that changes made to one copy of the database are propagated to the other copies in a consistent manner.

1. Master-Slave Replication: 
	1. In master-slave replication, there is one primary database server known as the master, and one or more secondary database servers known as slaves. 
	2. The master server handles write operations (updates, inserts, deletes) and propagates the changes to the slave servers. 
	3. The slave servers are read-only and serve read operations, relieving the master server from read-related load. 
	4. Master-slave replication provides high availability and scalability for read-heavy workloads but introduces replication lag between the master and slaves.
    
2. Master-Master Replication: 
	1. In master-master replication, multiple database servers act as both masters and slaves simultaneously. 
	2. Each server can handle write and read operations independently. 
	3. Changes made on one server are propagated to other servers, ensuring data consistency. 
	4. Master-master replication provides better scalability and fault tolerance since multiple servers can handle read and write operations. 
	5. It requires careful conflict resolution mechanisms to handle simultaneous writes on different servers.
    
3. Multi-Site Replication: 
	1. Multi-site replication involves replicating a database across geographically distributed sites or data centers. 
	2. This technique improves data availability and disaster recovery capabilities by maintaining copies of the database in different locations. 
	3. Changes made to one site are replicated to other sites asynchronously or synchronously, depending on the replication configuration. 
	4. Multi-site replication helps to mitigate the impact of localized failures or disasters on the availability of data.
    
4. Read Replicas: 
	1. Read replicas, also known as replica sets or read-only replicas, are additional copies of a database that serve read operations to offload the primary database. 
	2. Read replicas receive data updates through replication from the primary database but do not handle write operations. 
	3. They provide scalability by distributing read traffic across multiple servers, improving overall system performance.
    
5. Transactional Replication: 
	1. Transactional replication focuses on replicating individual database transactions from the primary server to the replicas. 
	2. It ensures that changes made to the database are consistently applied to all replicas, maintaining data integrity. 
	3. Transactional replication is commonly used in scenarios where strict consistency is required across multiple database instances.
    
6. Snapshot Replication: 
	1. Snapshot replication involves taking periodic snapshots of the primary database and replicating the entire snapshot to the replicas. 
	2. This technique is suitable when near real-time data consistency is not critical, and periodic updates are sufficient. 
	3. Snapshot replication is often used for data warehousing, reporting, or archival purposes.
    