## Push CDNs

1. Push CDNs receive new content whenever changes occur on your server. 
2. You take full responsibility for providing content, uploading directly to the CDN and rewriting URLs to point to the CDN. 
3. You can configure when content expires and when it is updated. 
4. Content is uploaded only when it is new or changed, minimizing traffic, but maximizing storage.

5. Sites with a small amount of traffic or sites with content that isn't often updated work well with push CDNs. 
6. Content is placed on the CDNs once, instead of being re-pulled at regular intervals.


In a Pull CDN, the content distribution is initiated by the client or end-user request. 
When a user requests a specific piece of content, such as a web page or a media file, the request is sent to the CDN's edge server closest to the user. 
If the requested content is not already cached on the edge server, the edge server retrieves it from the origin server (the source of truth for the content).

The edge server then caches the content and delivers it back to the user.
Subsequent requests for the same content from other users in the same geographical area can be served directly from the cache of the edge server, reducing the load on the origin server and improving response times.

Pull CDNs offer flexibility and scalability since content is fetched from the origin server only when requested, reducing the need for pre-caching. 
This approach is commonly used for dynamic content, personalized content, and frequently changing content.

