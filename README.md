# 🚀 **Docker Complete Guide**  

## 📌 **Overview**  
This repository contains a **comprehensive guide to Docker** 🐳, covering essential concepts, hands-on demonstrations, and advanced features like **Docker Compose, Networking, and Image Management**.  

---

## 📚 **Topics Covered**  

### 🔹 **Introduction to Docker**  
📌 Understanding **Docker** and its importance in software development.  
📌 Difference between **Docker Images** and **Containers**.  
📌 Basic **Docker commands** and key concepts.  

### 🔹 **Why Docker?**  
💡 Challenges in traditional software development workflows.  
💡 How Docker resolves **dependency conflicts** and ensures a **consistent environment**.  

### 🔹 **Docker Containers & Images**  
🔹 What are **Containers**?  
🔹 How Docker **Images** act as blueprints for containers.  
🔹 Portability 🏗️ and Scalability 🚀 benefits.  

### 🔹 **Practical Docker Setup & Commands**  
🔧 Installing **Docker Desktop**.  
🔧 Running containers (`docker run`, `docker ps`, `docker stop`).  
🔧 Managing images (`docker pull`, `docker rmi`).  

### 🔹 **Advanced Docker Features**  
🌍 **Port Binding & Networking** between containers.  
🛠️ **Troubleshooting** (`docker logs`, `docker exec`).  
⚖️ Differences between **Docker** & **Virtual Machines**.  

### 🔹 **Docker in Application Development**  
💻 Using Docker for **small-scale projects** and **team collaborations**.  
🛠️ Building a **Node.js** 🟢 app with **MongoDB** inside **Docker containers**.  

### 🔹 **Docker Databases & Networking**  
🛢️ Running **MongoDB** inside a container.  
🔗 Using **Docker Networks** for seamless container communication.  
📊 Running **Mongo Express** as a UI for MongoDB.  

### 🔹 **Docker Compose**  
⚙️ Simplifying **multi-container applications**.  
📝 Writing `docker-compose.yml` for **MongoDB & Mongo Express**.  
💾 Handling **data persistence** with **Docker Volumes**.  

### 🔹 **Dockerizing Applications**  
📦 Creating **Dockerfiles** to package applications.  
🖼️ Understanding **base images** and configuring **environment variables**.  
🚀 Building and running **custom Docker images**.  

### 🔹 **Pushing Images to Docker Hub**  
📤 Creating a **Docker Hub** account.  
📥 Pushing and pulling **Docker Images**.  
🌐 Docker **Networking** concepts and **Container Communication**.  

---

## 🚀 **Getting Started**  

### 🔹 **Prerequisites**  
Ensure you have the following installed:  
✅ [Docker Desktop](https://www.docker.com/products/docker-desktop)  
✅ [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)  
✅ [Docker Hub Account](https://hub.docker.com/) (Optional for image hosting)  

---

### 🔹 **Clone the Repository**  
```sh
git clone https://github.com/Hifza-Khalid/docker-complete-guide.git
cd docker-complete-guide
```

---

## 🏗️ **Running the Example Application**  

### **1️⃣ Run MongoDB in a Docker Container**  
```sh
docker run --name mongodb -d -p 27017:27017 mongo
```

### **2️⃣ Run Mongo Express for MongoDB Management**  
```sh
docker run --name mongo-express -d -p 8081:8081 --link mongodb:mongo mongo-express
```

### **3️⃣ Verify Running Containers**  
```sh
docker ps
```

---

## ⚡ **Using Docker Compose**  
Run the following command to start **MongoDB & Mongo Express** using Docker Compose:  
```sh
docker-compose up -d
```

Here’s a sample `docker-compose.yml` file:  

```yaml
version: '3'
services:
  mongodb:
    image: mongo
    container_name: mongodb
    ports:
      - "27017:27017"

  mongo-express:
    image: mongo-express
    container_name: mongo-express
    ports:
      - "8081:8081"
    environment:
      - ME_CONFIG_MONGODB_SERVER=mongodb
```

---

## 🏗️ **Building a Custom Docker Image**  
Create and run an **application container** using a custom **Dockerfile**:  
```sh
docker build -t my-app .
docker run -d -p 3000:3000 my-app
```

---

## 📤 **Pushing to Docker Hub**  
Replace `your-dockerhub-username` with your actual **Docker Hub** username before running these commands:  
```sh
docker tag my-app Hifza-Khalid/docker-complete-guide
docker push Hifza-Khalid/docker-complete-guide
```

---

## 🛠️ **Docker Commands Cheat Sheet**  
📄 A **PDF containing all essential Docker commands** is included in this repository for quick reference.  

---

## ⚠️ **Troubleshooting Common Issues**  

🔹 **Port Already in Use Error**  
❌ **Error:** `bind: address already in use`  
✅ **Fix:** Stop and remove the conflicting container:  
```sh
docker stop <container_id> && docker rm <container_id>
```

🔹 **Docker Daemon Not Running**  
❌ **Error:** `Cannot connect to the Docker daemon`  
✅ **Fix:** Start the Docker service:  
```sh
sudo systemctl start docker
```

🔹 **Image Pull Failure**  
❌ **Error:** `Error response from daemon: pull access denied`  
✅ **Fix:** Ensure you're logged in to Docker Hub:  
```sh
docker login
```

---

## 📝 **Contributing**  
🚀 Contributions are **welcome**! Submit **pull requests** for enhancements, bug fixes, or additional examples.  

---

## 📜 **License**  
📄 This project is licensed under the **MIT License**.  

---

## 📧 **Contact**  
📩 For **queries or discussions**, open an **issue** or reach out via **GitHub discussions**.  
