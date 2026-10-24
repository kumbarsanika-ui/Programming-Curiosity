# Cloud and deployment: challenge answers

## Questions 81–90: Real-world software

### 81. Where does your application actually run after deployment?

It runs on computing hardware in a data center, on a server, or on a user's device, depending on the application. Cloud platforms provide access to data-center resources, but the application still executes on physical processors and uses memory, storage, and networks.

### 82. What happens when one user uses your application?

The user's device runs the client interface and sends requests to a service. The server processes each request, may access databases or other services, and returns a response. The client displays the result. Even one user may cause several network and storage operations.

### 83. What changes when one million users use it?

Traffic, data volume, and concurrent work increase. A system may need more application instances, load balancing, caching, queues, database optimization, monitoring, and capacity planning. Bottlenecks and failures become more likely; scaling is measured and designed, not just assumed.

### 84. Why can’t we simply buy one huge computer?

A larger machine has limits in cost, capacity, availability, and upgradeability. It is also a single failure point. Multiple machines can share work and improve resilience, though distributed systems introduce networking, coordination, and consistency challenges.

### 85. What is a server?

A server is a program or computer that provides a service to clients. A web server accepts requests and returns responses; it may run application code, serve files, or forward work to other services. “Server” describes a role, not necessarily a special kind of hardware.

### 86. What is cloud computing?

Cloud computing provides computing resources and managed services over a network. Customers can provision servers, storage, databases, and networking without operating every physical machine themselves. They still need to configure, secure, monitor, and pay for the resources they use.

### 87. What is AWS or Azure actually providing?

Providers such as AWS and Azure offer data-center infrastructure and services: virtual machines, object storage, databases, networking, identity controls, monitoring, and managed runtimes, among many others. The provider operates some layers; the customer remains responsible for the application and customer-configured security.

### 88. What happens when a server crashes?

Requests to that instance may fail or time out. Monitoring and health checks can detect the failure; a load balancer can stop routing traffic to it, and an orchestrator may restart or replace it. Recovery depends on redundancy, saved state, and whether dependent services remain healthy.

### 89. How do Netflix, YouTube, or Instagram handle millions of users?

Large services combine distributed application servers, databases, caches, queues, content-delivery networks, load balancing, replication, and automated operations. Designs vary and evolve. They monitor bottlenecks and failures and use redundancy; no single trick guarantees reliable scale.

### 90. If you had to build WhatsApp from scratch, what would you need?

At minimum: client applications, identity and contact management, secure message APIs, persistent message storage, delivery and presence systems, push notifications, media storage, encryption design, abuse prevention, backups, monitoring, and reliable infrastructure. A real messaging service also needs privacy, accessibility, operations, and a plan for growth.

## Follow the trail

Read about [servers](./server.md), [cloud](./cloud.md), and [scaling](./scaling.md).
