
## Content delivery network

![[Pasted image 20230717230149.png]]

1. A content delivery network (CDN) is a globally distributed network of proxy servers, serving content from locations closer to the user. 
2. Generally, static files such as HTML/CSS/JS, photos, and videos are served from CDN, although some CDNs such as Amazon's CloudFront support dynamic content. 
3. The site's DNS resolution will tell clients which server to contact.

Serving content from CDNs can significantly improve performance in two ways:

	- Users receive content from data centers close to them
	- Your servers do not have to serve requests that the CDN fulfills

### Push CDNs
[[Push CDNS]]

### Pull CDNs
[[Pull CDNs]]

### Disadvantage(s): CDN

- CDN costs could be significant depending on traffic, although this should be weighed with additional costs you would incur not using a CDN.
- Content might be stale if it is updated before the TTL expires it.
- CDNs require changing URLs for static content to point to the CDN.


It's worth noting that some CDNs may incorporate elements of both Pull and Push approaches, depending on the specific requirements of the content and the system design.

The choice between Pull CDN and Push CDN depends on factors such as the nature of the content, frequency of updates, scalability needs, and the desired level of control over content distribution. 
Both approaches aim to enhance content delivery, reduce latency, and improve overall user experience by leveraging a distributed network of edge servers.
