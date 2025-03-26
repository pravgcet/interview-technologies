# Load Balancers

A **Load Balancer** is a device or software that distributes incoming network traffic across multiple servers to ensure no single server becomes overwhelmed. It optimizes resource use, improves response times, and enhances fault tolerance.

## Why Use Load Balancers?

- Prevent server overload.
- Improve availability and reliability.
- Enhance performance by distributing requests.
- Enable scaling by adding or removing servers dynamically.

## Types of Load Balancers:

1. **Layer 4 (Transport Layer) Load Balancer:**

   - Operates at the transport layer (TCP/UDP).
   - Distributes traffic based on IP address and port.
   - Example: AWS Network Load Balancer.

2. **Layer 7 (Application Layer) Load Balancer:**

   - Operates at the application layer (HTTP/HTTPS).
   - Makes routing decisions based on content, such as URL paths or headers.
   - Example: AWS Application Load Balancer.

3. **Hardware Load Balancer:**

   - Dedicated physical device for traffic distribution.
   - Example: F5 BIG-IP, Citrix ADC.

4. **Software Load Balancer:**

   - Runs on standard servers, often in cloud environments.
   - Example: NGINX, HAProxy.

5. **Global Load Balancer:**
   - Balances traffic across multiple geographic regions.
   - Example: Cloudflare, Azure Traffic Manager.

## Examples of Load Balancers in Action:

1. **E-commerce Websites:** Distributes customer requests to different servers to handle high traffic.
2. **Streaming Services:** Balances video streaming requests to optimize performance.
3. **Microservices Architecture:** Routes requests to various microservices, ensuring smooth communication.
4. **Kubernetes Ingress Controller:** Manages traffic into Kubernetes clusters.
