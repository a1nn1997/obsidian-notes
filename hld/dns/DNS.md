
1. A Domain Name System (DNS) translates a domain name such as [www.example.com](http://www.example.com/) to an IP address.

2. DNS is hierarchical, with a few authoritative servers at the top level. 
3. Your router or ISP provides information about which DNS server(s) to contact when doing a lookup. 
4. Lower level DNS servers cache mappings, which could become stale due to DNS propagation delays. 
5. DNS results can also be cached by your browser or OS for a certain period of time, determined by the [time to live (TTL)](https://en.wikipedia.org/wiki/Time_to_live).

- **NS record (name server)** - Specifies the DNS servers for your domain/subdomain.
- **MX record (mail exchange)** - Specifies the mail servers for accepting messages.
- **A record (address)** - Points a name to an IP address.
- **CNAME (canonical)** - Points a name to another name or `CNAME` (example.com to [www.example.com](http://www.example.com/)) or to an `A` record.

Services such as [CloudFlare](https://www.cloudflare.com/dns/) and [Route 53](https://aws.amazon.com/route53/) provide managed DNS services. Some DNS services can route traffic through various methods:

- [Weighted round robin](https://www.jscape.com/blog/load-balancing-algorithms)
    - Prevent traffic from going to servers under maintenance
    - Balance between varying cluster sizes
    - A/B testing
- [Latency-based](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html#routing-policy-latency)
- [Geolocation-based](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html#routing-policy-geo)

### Disadvantage(s): DNS

- Accessing a DNS server introduces a slight delay, although mitigated by caching described above.
- DNS server management could be complex and is generally managed by [governments, ISPs, and large companies](http://superuser.com/questions/472695/who-controls-the-dns-servers/472729).
- DNS services have recently come under [DDoS attack](http://dyn.com/blog/dyn-analysis-summary-of-friday-october-21-attack/), preventing users from accessing websites such as Twitter without knowing Twitter's IP address(es).

The Time-to-Live (TTL) value in a resource record indicates a length of time used by other DNS servers to determine how long to cache information for a record before expiring and discarding it.

## DNS architecture

DNS architecture is a hierarchical distributed database and an associated set of protocols that define:

- A mechanism for querying and updating the database.
    
- A mechanism for replicating the information in the database among servers.
    
- A schema of the database.


# **DNS Delegation**

![[Pasted image 20230717225146.png]]


# **DNS Query Types**

![[Pasted image 20230717225214.png]]


# **DNS Client Service Architecture**

![[Pasted image 20230717225230.png]]


# **DNS Server Service Architecture**

![[Pasted image 20230717225402.png]]

