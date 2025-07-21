# Hosting React App Using Custom Docker Image and Kubernetes Deployment Set & NodePort 🚀

This project demonstrates how to **host a React application** using a **custom Docker image** and manage its deployment on Kubernetes with a Deployment set and NodePort service. 🐳 ☸️

## Table of Contents

- [Project Overview](#project-overview) 📖
- [Prerequisites](#prerequisites) ✅
- [Project Structure](#project-structure) 🗂️
- [Usage Instructions](#usage-instructions) ⚡
  - [1. Clone the Repository](#1-clone-the-repository) 🛒
  - [2. Build the Docker Image](#2-build-the-docker-image) 🛠️
  - [3. Push Image to Registry (Optional)](#3-push-image-to-registry-optional) 📦
  - [4. Deploy on Kubernetes](#4-deploy-on-kubernetes) ☸️
- [Kubernetes Manifest Files](#kubernetes-manifest-files) 📄
- [Accessing the Application](#accessing-the-application) 🌐
- [License](#license) 📜

## Project Overview 📖

This repository shows how to:
- Build a React application with a custom Dockerfile ⚛️
- Containerize the React app 🐳
- Deploy the Docker container to a Kubernetes cluster using a Deployment YAML file ☸️
- Expose the application using a NodePort service for external access 🌍

## Prerequisites ✅

Before you begin, make sure you have:
- Docker installed and running 🐳
- Kubernetes cluster (local or cloud) and `kubectl` configured ☸️
- Node.js and npm (for building React app) 🟢
- (Optional) Docker Hub or another container registry account 📦

## Project Structure 🗂️

| File / Folder   | Description                              |
|-----------------|------------------------------------------|
| `Dockerfile`    | Dockerfile for building the React app image |
| `currency.yml`  | Kubernetes Deployment YAML                |
| `nodeport.yml`  | Kubernetes NodePort Service YAML          |
| `/src`          | React application source code (if added)  |

## Usage Instructions ⚡

### 1. Clone the Repository 🛒

```sh
git clone https://github.com/Rudra-Langote/react-project-with-dokerfile-kubernetes
cd react-project-with-dokerfile-kubernetes
```

### 2. Build the Docker Image 🛠️

```sh
docker build -t your-username/react-app:latest .
```

### 3. Push Image to Registry (Optional) 📦

```sh
docker login
docker push your-username/react-app:latest
```

Update the image name in the Kubernetes manifests (`currency.yml`, `nodeport.yml`) if you changed the name.

### 4. Deploy on Kubernetes ☸️

Apply the deployment and the NodePort service:

```sh
kubectl apply -f currency.yml
kubectl apply -f nodeport.yml
```

## Kubernetes Manifest Files 📄

### Deployment (`currency.yml`)

- Defines the pods and replicas for running the Dockerized React app ⚛️

### NodePort Service (`nodeport.yml`)

- Exposes the pods on a specific TCP port so the app is accessible from outside the Kubernetes cluster 🛣️

## Accessing the Application 🌐

After deployment, you can access the React app via your Kubernetes node’s external IP and the NodePort specified in `nodeport.yml`.

1. Get the NodePort:
    ```sh
    kubectl get service
    ```
2. Access via browser:
    ```
    http://:
    ```
Replace `` and `` with your values. 🌍

## License 📜

No license specified. Please check with the repository owner for intended use.

**Note:** For any issues or improvements, please open an issue or submit a pull request in the repository.
