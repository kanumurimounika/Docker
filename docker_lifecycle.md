# 🐳 Docker Lifecycle & Architecture

Docker is an OS‑level virtualization (containerization) platform that allows applications to share the host OS kernel instead of running separate operating systems like traditional Virtual Machines (VMs). This makes Docker lightweight, fast, portable, and isolated.

---

## 🚫 Before Docker

Before Docker, deploying applications across environments caused issues due to dependency mismatches, different OS configurations, and library version conflicts. This resulted in the famous problem: *"Works on my machine"*.

---

## ✅ Docker’s Solution

Docker standardizes the runtime environment by bundling application code, dependencies, runtime, and configuration into a single unit called an Image.

Benefits include portability, consistency across environments, lightweight execution, scalability for microservices, and efficient startup times.

---

## 🆚 Containers vs Virtual Machines

Containers share the host OS kernel and are lightweight, whereas virtual machines include a full OS and are heavier. Containers start quickly and use fewer resources.

---

## 🏗️ Docker Architecture

Docker uses a client-server architecture where the Docker Client communicates with the Docker Daemon using a REST API.

- Docker Client: CLI interface (docker run, docker build)
- Docker Daemon: Background service managing containers and images
- Docker Registry: Storage for images (Docker Hub)

---

## ⚙️ Docker Engine

Docker Engine is the core runtime that builds and runs containers.

Flow: docker command → REST API → Docker Daemon → container execution

---

## 📄 Dockerfile

A Dockerfile is a text file with instructions to build an image. Instructions are executed from top to bottom.

Example:

```dockerfile
FROM ubuntu:latest

WORKDIR /app

COPY . .

RUN apt-get update && apt-get install -y python3 python3-pip

CMD ["python3", "app.py"]
```

---

## 🧱 Docker Image

A Docker Image is a read-only template containing application code, dependencies, and configurations. It acts as a blueprint.

---

## 📦 Docker Container

A Docker Container is a running instance of an image. It is lightweight, isolated, and shares the host OS kernel.

---

## 🔄 Image vs Container

Image = Blueprint (static)
Container = Running instance (dynamic)

---

## ☁️ Docker Hub

Docker Hub is a cloud-based registry used to store and share Docker images. It supports public and private repositories and provides official images for common software.

---

## 🔧 Common Docker Commands

Run container:
```
docker run nginx
```

Pull image:
```
docker pull ubuntu
```

List containers:
```
docker ps
```

Stop container:
```
docker stop <container_id>
```

Start container:
```
docker start <container_id>
```

Login:
```
docker login
```

---

## 🧩 Docker Editions

- Community Edition (CE): Free and open-source
- Enterprise Edition (EE): Paid with advanced security and support

---

## 🔄 Docker Lifecycle

1. Write Dockerfile
2. Build Image (docker build)
3. Store in Registry (Docker Hub)
4. Pull Image (docker pull)
5. Run Container (docker run)
6. Manage Container (start, stop, restart)

---

## ✅ Conclusion

Docker simplifies application deployment by ensuring consistency, portability, and efficiency. It is widely used in modern DevOps workflows and works seamlessly with orchestration tools like Kubernetes.
