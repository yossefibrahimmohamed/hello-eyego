# hello-eyego
Hello Eyego is a Projcet App

# 👋 Hello Eyego – Simple Node.js App with Docker & Kubernetes

This is a simple Node.js web app that returns a friendly `Hello Eyego` message via an API.

Note:
Deployment to Amazon Web Services (AWS) has not been completed due to the requirement of a valid credit card for account activation.
As this project is intended for learning and demonstration purposes, and to avoid any unintended charges, the application is currently hosted locally and available via Docker Hub.

The setup, however, is fully compatible with AWS EKS, and all Kubernetes manifests are included in the project for future deployment.

![Screenshot 2025-07-23 202254](https://github.com/user-attachments/assets/abf29b7c-adc3-4228-8e2d-151f6712ed14)


It demonstrates:

- Containerization with **Docker**
- Deployment on **Kubernetes (EKS - AWS)**
- Automation using **GitHub Actions**
- Modular structure ready for **migration to GCB (Google Cloud Build)** or **Alibaba Cloud**

---

## 🚀 Live API

> Base URL: `http://<load-balancer-dns>/`

**GET /** → `Hello Eyego`

---

## 📦 Project Structure

hello-eyego/
├── index.js # Node.js App Entry
├── package.json # App dependencies
├── Dockerfile # For containerization
├── deployment.yaml # Kubernetes deployment
├── service.yaml # Kubernetes service
└── .github/workflows/
└── deploy.yml # GitHub Actions CI/CD pipeline


---

## 🧑‍💻 Run Locally

```bash
git clone https://github.com/yossefibrahimmohamed/hello-eyego.git
cd hello-eyego
npm install
node index.js
```

Then visit: http://localhost:3000
🐳 Docker
Build & Run:

```
docker build -t hello-eyego.
docker run -p 3000:3000 hello-eyego
```

☸️ Kubernetes (AWS EKS)
Prerequisites:
``
    AWS CLI & EKS configured

    kubectl installed
```

Deploy:

```
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

🔁 GitHub Actions

```
On every push to main:

```
    Automatically applies Kubernetes manifests

    Assumes image already pushed to Docker Hub

```
Secrets required:

```
    AWS_ACCESS_KEY_ID

    AWS_SECRET_ACCESS_KEY

```
