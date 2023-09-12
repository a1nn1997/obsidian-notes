## Pull CDNs
1. Pull CDNs grab new content from your server when the first user requests the content. 
2. You leave the content on your server and rewrite URLs to point to the CDN. 
3. This results in a slower request until the content is cached on the CDN.

A [time-to-live (TTL)](https://en.wikipedia.org/wiki/Time_to_live) determines how long content is cached. 
4. Pull CDNs minimize storage space on the CDN, but can create redundant traffic if files expire and are pulled before they have actually changed.

5. Sites with heavy traffic work well with pull CDNs, as traffic is spread out more evenly with only recently-requested content remaining on the CDN.

In a Push CDN, the content distribution is initiated by the content provider or the origin server itself. 
The content provider pushes the content to the edge servers proactively, before any user requests. 

This pre-caching allows the edge servers to store and serve the content immediately upon request, without needing to fetch it from the origin server.

Push CDNs are beneficial for static content that doesn't change frequently, as it can be pre-cached and distributed to the edge servers in advance. 
This approach reduces the reliance on the origin server and can improve performance by minimizing latency.

Push CDNs are often used for delivering large files, software updates, or media content that is expected to experience high demand or traffic surges.

