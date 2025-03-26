## Cache

A **Cache** is a temporary storage layer that stores copies of frequently accessed data to reduce latency and improve performance. It helps applications retrieve data faster by avoiding repeated access to slower backend systems.

### Key Responsibilities of a Cache:

- **Data Caching:** Temporarily stores frequently requested data to reduce backend load.
- **Response Caching:** Stores API responses to serve repeated requests faster.
- **Session Management:** Keeps track of user sessions in distributed systems.
- **Rate Limiting Support:** Works alongside rate limiting to track request counts efficiently.
- **Reducing Latency:** Minimizes the time taken to fetch data by providing a closer data source.
- **Fault Tolerance:** Provides fallback data during backend failures.

### Examples of Caches:

1. **Redis:**

   - In-memory data structure store used as a database, cache, and message broker.
   - Ideal for real-time applications.

2. **Memcached:**

   - High-performance distributed memory caching system.
   - Used to speed up dynamic database-driven websites.

3. **Cloudflare Cache:**

   - Caches content at the edge of the network to reduce latency.

4. **Varnish Cache:**

   - Focuses on HTTP caching and is commonly used for websites with heavy traffic.

5. **CDNs (Content Delivery Networks):**
   - Services like Akamai or CloudFront cache static content close to users.
