## Availability patterns
Design techniques and strategies employed to ensure high availability of a system. 
These patterns focus on minimizing downtime, maintaining continuous service, and maximizing system uptime. 
By incorporating availability patterns, system designers can enhance resilience, fault tolerance, and overall system reliability. Here are some commonly used availability patterns:

1. Redundancy: 
	1. Redundancy involves duplicating critical components or services within a system to eliminate single points of failure. 
	2. By introducing redundancy, if one component or service fails, another can seamlessly take over, ensuring continuous operation. 
	3. Redundancy can be implemented at various levels, 
		1. including hardware redundancy (such as using multiple servers), 
		2. software redundancy (such as running multiple instances of an application), 
		3. data redundancy (such as replicating data across multiple storage locations).

2. Load Balancing: 
3. Failover: 
	1. Failover is a mechanism that automatically switches to a backup system or component when the primary system or component fails. 
	2. It ensures minimal downtime by quickly and transparently transitioning to the backup, allowing the system to continue operating without interruption. 
	3. Failover patterns often involve redundant systems or components that are continuously synchronized, enabling seamless failover in the event of a failure.

4. Replication: 
	1. Replication involves creating and maintaining multiple copies of data or services across distributed locations. 
	2. Replication enhances availability by ensuring that if one copy becomes inaccessible or fails, other copies can be used to continue providing service. 
	3. Replication patterns can include database replication, content delivery networks (CDNs), or distributed file systems, depending on the specific requirements of the system.

5. Graceful Degradation: 
	1. Graceful degradation is a pattern that allows a system to continue functioning, albeit with reduced functionality, even in the presence of failures or adverse conditions. 
	2. When faced with resource constraints or failures, the system intelligently adapts and prioritizes critical functionalities while temporarily disabling or reducing non-essential features. 
	3. By gracefully degrading in such scenarios, the system ensures that it remains available and operational, albeit with a diminished scope of functionality.

6. Isolation and Microservices: 
	1. Isolation patterns emphasize dividing a system into smaller, independent services or microservices. 
	2. Each microservice can operate autonomously, providing a more resilient and fault-tolerant architecture. 
	3. If one microservice fails, it does not bring down the entire system, as other microservices can continue functioning independently. 
	4. Isolation patterns help prevent cascading failures and enable easier scalability and maintenance of individual components.

These availability patterns can be combined and tailored based on specific system requirements, scalability needs, and business objectives. The goal is to create a robust and highly available system that can withstand failures, adapt to changing conditions, and ensure uninterrupted service to users.

## Availability patterns

There are two complementary patterns to support high availability: **fail-over** and **replication**.

### Fail-over

#### Active-passive

	With active-passive fail-over, heartbeats are sent between the active and the passive server on standby. If the heartbeat is interrupted, the passive server takes over the active's IP address and resumes service.

	The length of downtime is determined by whether the passive server is already running in 'hot' standby or whether it needs to start up from 'cold' standby. Only the active server handles traffic.

	Active-passive failover can also be referred to as master-slave failover.

#### Active-active

	In active-active, both servers are managing traffic, spreading the load between them.

	If the servers are public-facing, the DNS would need to know about the public IPs of both servers. If the servers are internal-facing, application logic would need to know about both servers.

	Active-active failover can also be referred to as master-master failover.

### Disadvantage(s): failover

	- Fail-over adds more hardware and additional complexity.
	- There is a potential for loss of data if the active system fails before any newly written data can be replicated to the passive.