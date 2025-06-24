### **DevOps Intern Assignment: Nginx Reverse Proxy + Docker**

You are expected to set up a docker compose based system:



1. **Download the source code for these services: <https://drive.google.com/drive/u/0/folders/1G4E1rmnUxlURxJZwc2AtQ9gy8Q2mwj3A>**
2. This contains two folders

   
   1. A golang application
   2. A python application
   3. The readme files in the two will explain how to run these.


Your first job is to put this in a .git repository and add the following files


### 📁 Project Structure

```
.
├── docker-compose.yml
├── nginx
|   └── nginx.conf
│   └── Dockerfile
├── service_1
│   └── Dockerfile
├── service_2
│   └── Dockerfile
└── README.md
```


The nginx reverse proxy should do the following 


1. **Nginx reverse proxy** (also in a Docker container) routes:
   * `/service1` requests to backend service 1
   * `/service2` requests to backend service 2
2. All services must be accessible via a single port (e.g., `localhost:8080`).


---

### ✅ **Requirements**


1. Use Docker Compose to bring up the entire system.
2. The Nginx config should support:
   * Routing based on URL path prefix (`/service1`, `/service2`)
   * Logging incoming requests with timestamp and path
3. The system should work with a single command:

   ```bash
   docker-compose up --build
   ```
4. Bonus: Add a health check for both services and show logs of successful routing.


---

### 📦 Tech Constraints

* Nginx must run in a Docker container, not on host
* Use bridge networking (no host networking)
