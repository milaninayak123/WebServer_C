# Multi-Threaded Proxy Server (With LRU Cache)

This project is built using **C** and focuses on HTTP parsing.

---

## 🔍 Overview

### ✨ Introduction
A **Multithreaded Proxy Web Server with LRU Cache** acts as a middleman between clients (like web browsers) and actual web servers. Here’s how it works:

1. **Receive Requests:** When a client (browser) requests a webpage, the proxy server intercepts and handles the request instead of directly contacting the website.
2. **Check Cache (LRU Cache):** Before fetching the webpage from the internet, it checks if a recent copy is stored in memory.
   - If the page is in the cache (**cache hit**), it serves the stored copy, making the process faster.
   - If not (**cache miss**), it fetches the page from the actual web server, stores it in the cache, and then returns it to the client.
3. **Use LRU (Least Recently Used) Policy:** If the cache is full, it removes the least recently used page to make space for new ones.
4. **Handle Multiple Requests (Multithreading):** It uses multiple threads to manage multiple client requests simultaneously, improving efficiency.

### 🚀 Why is this Useful?
- **Faster Browsing:** Cached pages load instantly.
- **Reduced Bandwidth Usage:** Less data is retrieved from the internet.
- **Handles Multiple Users:** Many clients can connect at the same time without experiencing delays.

### 🛡 Role of a Proxy Server
A proxy server plays a crucial role in:
- **Enhancing speed & reducing traffic** to main servers.
- **Restricting access** to specific websites.
- **Hiding the client’s IP address** for privacy.
- Modifying requests to **encrypt traffic** for improved security.

---

## ⚙ OS Components Used
- **Threading** for handling multiple requests.
- **Locks** for concurrency control.
- **Semaphores** for thread synchronization.
- **Cache (LRU Algorithm)** for optimizing response times.

---

## ⚠ Limitations
- If a URL loads multiple clients on its own, the cache stores them separately, which may cause partial retrieval issues.
- The cache has a **fixed size**, meaning large websites might not be stored entirely.

---

## 🔧 Future Enhancements
Potential improvements to the project:
- Implementing **multiprocessing** for better parallelism.
- Adding **website access control** mechanisms.
- Extending support for **POST requests** along with GET requests.

---
