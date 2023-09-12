Divide a database's data into smaller, more manageable units called partitions. 
Each partition contains a subset of the data and is stored on separate physical or logical storage locations. 
Partitioning improves performance, scalability, and manageability by allowing operations to be performed on individual partitions instead of the entire dataset.

1. Range Partitioning: 
	1. Range partitioning involves dividing the data based on a specified range of values. 
	2. For example, a database table could be partitioned based on date ranges, where each partition contains data for a specific time period, such as months or years.
	3. Range partitioning is useful when data access or maintenance is typically performed on specific ranges.

3. List Partitioning: 
	1. List partitioning involves dividing the data based on predefined lists or value sets. 
	2. Each partition is assigned a list of specific values that determine which data rows belong to that partition. 
	3. For instance, a customer database could be partitioned based on geographic regions, where each partition contains customers from a particular region. 
	4. List partitioning is suitable when data can be categorized into distinct groups.

5. Hash Partitioning: 
	1. Hash partitioning distributes data across partitions based on the result of applying a hash function to a specific column or columns. 
	2. The hash function evenly distributes the data, ensuring that rows with similar values are distributed across different partitions. 
	3. Hash partitioning is effective when a uniform distribution of data is desired, and there is no specific range or list to base the partitioning on.

7. Composite Partitioning: 
	1. Composite partitioning involves combining multiple partitioning techniques to create a more flexible partitioning scheme. 
		1. For example, a database table can be partitioned first using range partitioning based on date ranges and then further partitioned using hash partitioning based on a customer ID. 
		2. Composite partitioning allows for more granular control and customization of data distribution.

9. Sub partitioning: 
	1. Sub partitioning is the process of dividing partitions into smaller sub partitions. 
	2. It allows for an additional level of partitioning within a partition. 
	3. Subpartitioning can be applied to any of the aforementioned partitioning techniques to further enhance manageability and performance.

11. Vertical Partitioning: 
	1. Vertical partitioning involves splitting a table's columns into separate partitions based on their logical grouping or usage patterns. 
	2. This technique allows for more efficient data access by storing frequently accessed columns in one partition and less frequently accessed columns in another. 
	3. Vertical partitioning can improve query performance by reducing I/O operations on less relevant columns.
