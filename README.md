# Software Engineering in Practice - Assignment 1

## Description

This project was created for Assignment 1 of the Software Engineering in Practice course.

The goal was to containerize a Node.js application using Docker, automate the build process with GitHub Actions and deploy the application on Kubernetes using Minikube.

---

## Repository

Repository link:

https://github.com/mariettakyriazi/seip_assignment_1_2026

---

## Clone Repository

```bash
git clone https://github.com/mariettakyriazi/seip_assignment_1_2026.git
cd seip_assignment_1_2026
```

---

## Docker

Build the image:

```bash
docker build -t echo-api .
```

Run the container:

```bash
docker run -p 3000:3000 echo-api
```

---

## GitHub Actions

A GitHub Actions workflow was created to:

- checkout the repository
- build the Docker image
- push the image to GitHub Container Registry

Docker image:

```text
ghcr.io/mariettakyriazi/echo-api:latest
```

---

## Kubernetes

Deploy the application:

```bash
kubectl apply -f k8s/
```

Check resources:

```bash
kubectl get all -n default
```

Check ConfigMap and Secret:

```bash
kubectl get configmap,secret
```

---

## Port Forwarding

```bash
kubectl port-forward service/echo-api-service 8080:80
```

Application:

```text
http://localhost:8080/
```

Secure endpoint:

```text
http://localhost:8080/secure-config
```

---

## AI Usage

I used ChatGPT to better understand Docker, GitHub Actions and Kubernetes concepts. It helped me understand the YAML files and troubleshoot some configuration issues.

However, I still had to test everything locally and solve problems related to Docker Desktop, WSL and Minikube.

---

## Future Improvements

If I had more time, I would further improve the project by adding:

- an Ingress Controller
- monitoring with Prometheus
- automated security scanning
* a GitOps workflow with ArgoCD

