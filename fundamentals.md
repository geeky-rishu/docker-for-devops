
# Docker Fundamentals Commands

This document organizes Docker fundamental commands in a topic-wise fashion with brief explanations where necessary.

---

## 1. Docker Installation Commands

### Update Package List
```bash
sudo apt-get update
```
- Updates the package list to ensure that all software information is up to date.

### Install Docker Engine
```bash
sudo apt-get install docker.io
```
- Installs Docker Engine, allowing you to manage and run containers on your system.

### Grant User Access to Docker
```bash
sudo usermod -aG docker ubuntu && newgrp docker
```
- Adds the user `ubuntu` to the `docker` group, enabling the use of Docker commands without `sudo`.

---

## 2. Docker Image Management

### Pull an Image
```bash
docker pull <image_name>
```
- Downloads a Docker image from Docker Hub.
- Example:
  ```bash
  docker pull mysql:latest
  ```

### List Downloaded Images
```bash
docker images
```
- Displays all the Docker images stored on your system.

---

## 3. Container Management

### Run a Container
```bash
docker run <image_name>
```
- Runs a container from the specified image.
- Example:
  ```bash
  docker run ubuntu
  ```

### Run a Container in Detached Mode
```bash
docker run -d <image_name>
```
- Starts the container in the background, allowing the terminal to be used for other tasks.
- Example:
  ```bash
  docker run -d mysql:latest
  ```

### Run a Container with Environment Variables
```bash
docker run -d -e <ENV_VAR>=<value> <image_name>
```
- Passes environment variables to the container.
- Example:
  ```bash
  docker run -d -e MYSQL_ROOT_PASSWORD=password mysql:latest
  ```

### List Running Containers
```bash
docker ps
```
- Shows currently running containers.

### List All Containers
```bash
docker ps -a
```
- Displays all containers, including stopped ones.

### Access a Running Container
```bash
docker exec -it <container_id> bash
```
- Opens an interactive terminal in the specified container.

---

## 4. Verification and Testing

### Verify Docker Installation
```bash
docker --version
```
- Checks the installed version of Docker.

### Test Docker Functionality
```bash
docker run hello-world
```
- Runs a test container to confirm Docker is working correctly.

---

## 5. Additional Notes
- Always use descriptive names or tags for images and containers for easier management.
- Use `docker logs <container_id>` to view logs from a container.
- Use `docker stop <container_id>` and `docker rm <container_id>` to stop and remove containers, respectively.

This document serves as a quick reference for fundamental Docker commands and their usage.
