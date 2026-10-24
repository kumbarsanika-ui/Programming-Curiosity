# Scaling

Scaling is changing a system's capacity to handle more work. Workload may grow in users, requests, stored data, or complexity.

## Vertical and horizontal scaling

Vertical scaling gives one machine more resources, such as memory or processor capacity. Horizontal scaling adds more machines or instances and distributes work among them. Vertical scaling can be simpler but has limits; horizontal scaling can expand further but introduces coordination and operational complexity.

## Bottlenecks

Performance is often limited by one part of a system: a slow database query, a network call, an overloaded server, or inefficient code. Measure the system before adding capacity. Caching, better indexes, queues, or optimized algorithms may help, but each adds trade-offs.

## Distributed systems

With multiple instances, the system must decide how to distribute requests, store shared state, handle failures, and deploy updates. A load balancer can route traffic across servers. Stateless application instances are often easier to scale, while shared data may require databases or other services.

## The key idea

Scaling is not simply adding servers. It is understanding the bottleneck and choosing a reliable way to increase capacity without losing correctness or making the system unnecessarily difficult to operate.
