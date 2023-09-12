To ensure that data remains consistent and coherent across different components or replicas within a distributed system. 
Maintaining consistency is crucial for data integrity and correctness.

1. Strong Consistency: 
	1. Strong consistency ensures that all replicas or components in a distributed system have the same view of the data at all times. 
	2. When a write operation completes, all subsequent read operations will see the updated data. 
	3. Strong consistency provides a linearizable or sequential consistency model. 
	4. Techniques such as two-phase commit (2PC) or consensus algorithms like Paxos or Raft are used to achieve strong consistency.

2. Eventual Consistency: 
	1. Eventual consistency allows for temporary inconsistencies between replicas, but guarantees that all replicas will eventually converge to a consistent state. 
	2. After a write operation, there may be a period of time called the "inconsistency window" during which different replicas may have different views of the data. 
	3. Eventually, all replicas will synchronize and reach a consistent state. 
	4. Conflict resolution techniques, such as vector clocks or reconciliation algorithms, are commonly used in achieving eventual consistency.

3. Read-your-Write Consistency: 
	1. Read-your-write consistency ensures that a read operation immediately following a write operation will always see the updated data. 
	2. This consistency pattern is often required in scenarios where strong consistency is not necessary throughout the system, but a specific relationship between a write and a subsequent read is desired. 
	3. Techniques like session consistency or client-specific timestamps are employed to enforce read-your-write consistency.

4. Monotonic Read Consistency: 
	1. Monotonic read consistency guarantees that if a process or replica observes a specific version of a data item, it will not observe an older version in the future. 
	2. This consistency pattern ensures that subsequent reads from the same or different processes will always return data that is at least as up-to-date as the initial read.
	3. Techniques like version vectors or read fences are used to achieve monotonic read consistency.

5. Read-After-Write Consistency: 
	1. Read-after-write consistency ensures that if a process or replica performs a write operation and then performs a subsequent read operation on the same data item, it will always see the written value. 
	2. This pattern is commonly employed to maintain causality in systems where preserving the order of write and read operations is important. 
	3. Techniques like quorum reads or write leases can be used to enforce read-after-write consistency.

6. Consistency Models: 
	1. Consistency models define the level of consistency provided by a distributed system. 
	2. Examples include strict consistency, linearizability, sequential consistency, causal consistency, and eventual consistency. 
	3. Each model specifies the rules and guarantees regarding how operations are ordered and how data is propagated across replicas.

7. Weak consistency
	1. After a write, reads may or may not see it. A best effort approach is taken.
	2. This approach is seen in systems such as memcached. 
	3. Weak consistency works well in real time use cases such as VoIP, video chat, and realtime multiplayer games. 
	4. For example, if you are on a phone call and lose reception for a few seconds, when you regain connection you do not hear what was spoken during connection loss.



