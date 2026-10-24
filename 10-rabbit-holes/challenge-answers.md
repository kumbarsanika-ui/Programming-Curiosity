# Rabbit-hole questions: answers and investigation trails

These answers connect topics across the repository. For each trail, ask why the system is built this way, what each component does, how data moves, where it is stored or processed, when failures matter, who is responsible for each step, and what would happen if a component or assumption changed.

## Questions 1–10

### 1. When I type `x = 10`, where exactly does `10` go?

The language evaluates `10` as an integer value and binds the name `x` to it in the current scope. In CPython, the integer is represented by a runtime-managed object in the process's virtual memory. The operating system maps virtual memory to physical RAM as needed. It is not meaningful to expect one permanent physical address: implementation, optimization, and execution can change the details.

**Trail:** variable → object → process memory → virtual address → physical memory → operating system.

### 2. When I type `python app.py`, what happens between pressing Enter and seeing the output?

The terminal sends the command to a shell. The shell locates Python and asks the operating system to start it as a process. The interpreter reads and parses the file, creates an executable representation, and runs it. The process may write output to a terminal, which displays it. Errors can occur during lookup, parsing, execution, or access to external resources.

**Trail:** terminal → shell → `PATH` lookup → process → interpreter → runtime → operating system → output device.

### 3. When I enter `google.com`, how does my computer find another computer somewhere in the world?

The browser asks DNS for a suitable address, using caches where available. The operating system sends packets toward that IP address through routers and network links. The browser establishes a connection, negotiates TLS for HTTPS, and sends an HTTP request. Large websites may route the request to a nearby or otherwise suitable server rather than one fixed computer.

**Trail:** browser → DNS resolver → IP address → router → network path → TLS → HTTP server.

### 4. When I click Login, how does my password travel from my phone to the server and come back as “Login successful”?

The app sends credentials to its service over HTTPS, which protects the connection in transit. The server validates the request, looks up the account, and verifies the submitted password against a salted password hash. It may apply additional checks, then creates a session or token. The response tells the app whether login succeeded; subsequent requests use the session credential. HTTPS does not make an unsafe server or compromised phone safe.

**Trail:** input → HTTPS request → server validation → password-hash verification → session/token → response → authorization on later requests.

### 5. When I upload a photo to Instagram, where does that photo actually go?

The app reads the selected image and sends it to a service, often directly to a media-storage endpoint using a temporary authorized upload. Servers validate metadata and permissions, may resize or transcode the image, and store original and derived versions in object storage. Database records connect the media to the account and post; caches and content-delivery networks help deliver it to viewers. The exact architecture is proprietary and may change.

**Trail:** device file → upload request → validation → media processing → object storage → database metadata → CDN delivery.

### 6. How can millions of people use the same application at the same time?

The service distributes requests among many application instances, often behind load balancers. Caches reduce repeated work; queues absorb bursts; databases and storage are configured for the required workload. Teams monitor bottlenecks and add capacity or redesign hot paths. Horizontal scaling also requires careful handling of shared state, failures, and data consistency.

**Trail:** clients → DNS/CDN → load balancer → application instances → cache/queue/database → monitoring and scaling.

### 7. What happens if two users try to modify the same database record at exactly the same time?

The database coordinates concurrent operations according to its transaction and isolation rules. Depending on the operation and design, one change may wait, conflict, fail, or overwrite another. Applications can prevent lost updates using transactions, row locks, optimistic version checks, or constraints, and should retry only when safe.

**Trail:** concurrent requests → transaction isolation → locks/version checks → commit or conflict → application retry or response.

### 8. How does a program know that another program has crashed?

Usually it does not know with certainty from one missed message. A supervising process, orchestrator, or service monitor checks exit status, health probes, or periodic heartbeats. A timeout suggests a failure but could also mean a slow network or overloaded service. Systems use retries and redundancy while accounting for false suspicions.

**Trail:** process exit/health probe/heartbeat → timeout or failure signal → supervisor → restart, reroute, or alert.

### 9. If Python, JavaScript, and Java are completely different languages, how can they communicate with each other?

They agree on a shared interface rather than sharing language syntax. For example, each program can send HTTP messages containing JSON; each language has libraries to encode and decode that format. They can also use databases, queues, files, native interfaces, or language-specific RPC protocols. Both sides must follow the same contract.

**Trail:** API contract → protocol → serialization → transport → receiving language parses and handles data.

### 10. If the internet disappeared tomorrow, which parts of your application would still work?

Anything installed and designed to run locally could continue: offline documents, local calculations, and cached data. Features that depend on remote APIs, cloud storage, authentication servers, or online updates may stop or become limited. Offline-capable apps explicitly store data locally and synchronize later, which introduces conflict and security questions.

**Trail:** local client and cache → unavailable network dependencies → offline behavior → local changes → later synchronization and conflict resolution.

## The seven-question lens

Use this set to take any answer further:

- **WHY?** What need or constraint led to this design?
- **WHAT?** What are the components, data, and terms involved?
- **HOW?** What sequence of steps makes it work?
- **WHERE?** Where does computation or storage happen?
- **WHEN?** At what point does a decision, update, or failure occur?
- **WHO?** Which people, programs, or services are responsible?
- **WHAT IF?** How does the system behave when an assumption fails or changes?

## Related guides

- [What happens when you run code?](./what-happens-when-you-run-code.md)
- [What happens when you open Google?](./what-happens-when-you-open-google.md)
- [How a login works](./how-a-login-works.md)
