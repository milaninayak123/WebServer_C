# Multi-Threaded Proxy Server (With & Without Cache)

This project is built using **C** and focuses on HTTP parsing.

---

## 📌 Index
- [Overview](#overview)
- [How to Run](#how-to-run)
- [Demo](#demo)
- [Contributing](#contributing)

---

##  Overview

###  Introduction
A **proxy server** acts as an intermediary between a client and the internet. Below is a simple workflow of how the proxy functions:

![Proxy Server Workflow](pics/UML.JPG)

### ⚡ Multi-threading Implementation
To achieve multi-threading, we used:
- **Semaphores** instead of **Condition Variables** and `pthread_join()`/`pthread_exit()`.
- Unlike `pthread_join()`, which requires a thread ID to wait for, **semaphores** (`sem_wait()` and `sem_post()`) function without additional parameters, making them more efficient in this scenario.

### 🚀 Why This Project?
The project was developed to understand:
- How a request from a local system reaches a server.
- Managing multiple client requests simultaneously.
- Ensuring proper locking mechanisms for concurrency.
- The caching mechanisms used by web browsers.

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
