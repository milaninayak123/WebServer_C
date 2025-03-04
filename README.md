# Multi-Threaded Proxy Server with and without Cache

This project is implemented using **C** and HTTP parsing.

## Index
- [Project Theory](#project-theory)
- [How to Run](#how-to-run)
- [Demo](#demo)
- [Contributing](#contributing)

---

## Project Theory
[Back to top](#index)

### **Introduction**
**Basic Working Flow of the Proxy Server:**

![Proxy Server Workflow](pics/UML.JPG)

### **How did we implement Multi-threading?**
- Used **Semaphore** instead of **Condition Variables** and `pthread_join()`/`pthread_exit()`.
- `pthread_join()` requires passing the thread ID to wait for.
- **Semaphore’s** `sem_wait()` and `sem_post()` do not need parameters, making it a better option.

### **Motivation/Need of the Project**
To Understand:
- How requests from a local computer reach a server.
- Handling multiple client requests.
- Locking procedures for concurrency.
- Cache functions used by browsers.

### **What Does a Proxy Server Do?**
- Speeds up processes and reduces server traffic.
- Restricts users from accessing specific websites.
- Hides the client's IP address from the server.
- Can be modified to **encrypt requests** and enhance security.

---

## **OS Components Used**
- **Threading**
- **Locks**
- **Semaphore**
- **Cache** (Uses **LRU algorithm**)

---

## **Limitations**
- If a URL loads multiple clients itself, the cache stores each response separately, leading to partial retrieval.
- The cache has a **fixed size**, so large websites may not be fully stored.

---

## **How This Project Can Be Extended**
- Implementing **multiprocessing** for parallel execution.
- Controlling **website access permissions**.
- Supporting **POST requests** in addition to GET.

---

