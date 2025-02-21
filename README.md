# Content Delivery Network (CDN) in C++

## Introduction
This project is a simple simulation of a Content Delivery Network (CDN) using C++. The program uses a queue to process content requests, a hash-based caching mechanism for local content storage, and a latency matrix to simulate the latency between different servers.

## Features
- Implements a queue for handling content requests (enqueue and dequeue operations)
- Uses a local cache to store frequently accessed content
- Simulates fetching content from the nearest server if not available in the cache
- Displays network latency between servers
- Allows users to display the current cache state

---
## Modules Explanation

### 1. Queue Implementation
- `enqueueAndDequeue()`: Handles the enqueue and dequeue operations for content requests.
- If the queue is full, an overflow message is displayed.
- If the queue is empty, an underflow message is displayed.
- Uses a circular queue structure with `front` and `rear` pointers.

### 2. Caching Mechanism
- Uses a simple hash function `h(contentID)` to determine cache placement.
- Checks whether content is already present in the cache.
- If not found, it fetches the content from a simulated server.
- Stores the fetched content in the local cache.

### 3. Latency Simulation
- The `g[MAX][MAX]` matrix stores predefined latency values between servers.
- The program simulates fetching content from the nearest server and displays the corresponding latency.

### 4. Content Fetching
- `fetchContent(int contentID, int cacheIndex)`: Simulates retrieving content from an origin server if not found in the cache.
- The retrieved content is stored in the cache for future requests.

### 5. Display Cache Table
- `Display_Table(string Table[])`: Displays the content stored in the cache.
- Shows the index and corresponding content or marks it as "Empty" if no content is stored.

---
## Sample Output
```
You are in Enqueue & Dequeue Operation
Enter content ID to request: 7
Content ID 7 enqueued.
Processing Content ID: 7
Content not found in cache. Checking server network...
Fetching content from the nearest server or origin for content ID: 7
Content fetched and cached: Content_7
Latency between the requesting server and the nearest server for content ID 7: 10 ms
Would you like to display the cache content? (y/n): y
Index   Content
0       Empty
1       Content of Website
2       Image
3       Empty
4       Empty
Do you want to continue? (y/n): n
```

---
## How to Run the Code
1. Compile the code using a C++ compiler:
   ```sh
   g++ -o cdn_simulator cdn.cpp
   ```
2. Run the executable:
   ```sh
   ./cdn_simulator
   ```
3. Follow the on-screen instructions to request content, check cache status, and continue or exit the simulation.

---
## Future Enhancements
- Implement a more dynamic queue with a linked list to handle a larger number of requests.
- Improve cache eviction policies using LRU or LFU.
- Use real-world latency data instead of a static latency matrix.

---
## License
This project is open-source and available under the MIT License.

