technique used to distribute incoming network traffic across multiple servers, ensuring optimal resource utilization, high availability, and improved performance. 
Load balancers act as intermediaries between clients and servers, distributing requests in a way that minimizes individual server overload and maximizes overall system efficiency. 

1. Round-robin load balancing: 
	1. Round-robin load balancing distributes incoming requests sequentially across a group of servers in a rotating manner. 
	2. Each server receives an equal number of requests in turn, ensuring a balanced distribution of the workload. 
	3. Round-robin load balancing is simple to implement and works well when servers have similar capacities.
    
2. Weighted round-robin load balancing: 
	1. Weighted round-robin load balancing is similar to round-robin, but it assigns different weights to servers based on their capacities. 
	2. Servers with higher weights receive a proportionally larger share of the traffic. 
	3. This approach allows administrators to allocate resources according to server capabilities and optimize the distribution of the workload.
    
3. Least Connection load balancing: 
	1. Least Connection load balancing assigns incoming requests to the server with the fewest active connections at the time. 
	2. This method ensures that servers with fewer active connections receive more requests, distributing the load based on real-time server utilization. 
	3. It is particularly useful in scenarios where the duration of each connection can vary significantly.
    
4. IP Hash load balancing: 
	1. IP Hash load balancing assigns incoming requests to servers based on the source IP address of the client. 
	2. The hash function generates a unique identifier based on the client's IP address, ensuring that subsequent requests from the same client are directed to the same server. 
	3. This approach helps maintain session persistence and is commonly used in scenarios where maintaining state between requests is crucial.
    
5. Least Response Time load balancing: 
	1. Least Response Time load balancing directs incoming requests to the server with the shortest response time. 
	2. This method measures the time it takes for each server to respond to previous requests and dynamically adjusts the load distribution accordingly. 
	3. Least Response Time load balancing aims to optimize performance by routing traffic to the server that can respond the fastest.
    
6. Dynamic load balancing: 
	1. Dynamic load balancing techniques use real-time monitoring and analysis of server health and performance metrics to determine the appropriate distribution of traffic. 
	2. These techniques consider factors such as server CPU utilization, memory usage, network latency, or application-specific metrics. 
	3. Dynamic load balancers continuously adapt the load distribution based on changing conditions, ensuring optimal resource allocation and performance.


![[Pasted image 20230717232913.png]]


Load balancers can be implemented with hardware (expensive) or with software such as HAProxy.

Additional benefits include:

###  **SSL termination** 
 - Decrypt incoming requests and encrypt server responses so backend servers do not have to perform these potentially expensive operations
- Removes the need to install [X.509 certificates](https://en.wikipedia.org/wiki/X.509) on each server
### **Session persistence** 
- Issue cookies and route a specific client's requests to same instance if the web apps do not keep track of session

The choice between [[4 layer loadbalancer]] and [[7 layer loadbalancer]] load balancing architectures depends on the specific requirements of your application. 
Layer 4 load balancing is efficient and performs well in scenarios where simple traffic distribution based on network protocols is sufficient. 
On the other hand, Layer 7 load balancing provides advanced routing capabilities and is ideal for applications that require content-based routing, SSL termination, or application-specific optimizations.

It's important to consider factors like application complexity, scalability needs, security requirements, and the level of control and customization required when deciding between Layer 4 and Layer 7 load balancing architectures for your system.

At the cost of flexibility, layer 4 load balancing requires less time and computing resources than Layer 7, although the performance impact can be minimal on modern commodity hardware.