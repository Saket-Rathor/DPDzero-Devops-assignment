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
├── docker-compose.yml
├── nginx
│   ├── nginx.conf
│   ├── Dockerfile
│   └── README.md
├── readme.md
├── service_1
│   ├── Dockerfile
│   ├── main.go
│   └── README.md
└── service_2
    ├── app.py
    ├── Dockerfile
    ├── pyproject.toml
    ├── README.md
    └── uv.lock
```

🚀 Getting Started
✅ Prerequisites
Make sure you have the following installed:

Docker
Docker Compose
git
Check Docker installation:

docker --version
docker compsose version
git --version
🛠 How to Run the Project
Clone the Repository

git clone <your-repo-url>
cd <project-directory>
Build and Start All Services

docker-compose up --build -d # -d for detach mode
This command will -:
Build Docker images for each service
Start containers for service_1, service_2, and nginx
View Running Containers

docker ps
Access the Application

Once the containers are up and running, open your browser and go to.
http://localhost # nginx
http://localhost/service1/ping # golang
http://localhost/service2/ping # python
🛑 Stopping the Project
To stop all containers and remove networks
docker-compose down
📜 View Logs from All Services
docker compse logs -f

You can also view logs for a specific service:
docker-compose logs -f service_1
docker-compose logs -f service_2
docker-compose logs -f nginx

📌 Notes
Ensure that required ports (e.g., 80, 8001, 8002) are not in use.


The nginx reverse proxy should do the following 


1. **Nginx reverse proxy** (also in a Docker container) routes:
   * `/service1` requests to backend service 1
   * `/service2` requests to backend service 2
2. All services must be accessible via a single port (e.g., `localhost:8080`).


### 📦 Tech Constraints

* Nginx must run in a Docker container, not on host
* Use bridge networking (no host networking)
