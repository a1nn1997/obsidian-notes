Layer 4 Load Balancing:

1. Operates at the Transport layer (Layer 4) of the OSI model.
2. Makes load balancing decisions based on information available at the network and transport layers, such as source IP address and port numbers.
3. Distributes traffic based on network protocols like TCP or UDP.
4. Focuses on routing requests based on the destination IP address and port number.
5. Typically performs simple packet forwarding without inspecting the contents of the packets.
6. Suitable for scenarios where applications are stateless and do not require advanced application-specific routing.
7. Offers efficient distribution of traffic and can handle a large number of concurrent connections.
8. Examples of Layer 4 load balancing solutions include hardware load balancers and software load balancers that work at the Transport layer.
9. Layer 4 load balancers look at info at the **transport layer** to decide how to distribute requests. Generally, this involves the source, destination IP addresses, and ports in the header, but not the contents of the packet. Layer 4 load balancers forward network packets to and from the upstream server, performing **Network Address Translation (NAT)**.
