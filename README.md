# ☸️ Kubernetes Voting Application

A complete microservices-based voting application deployed on a local Kubernetes cluster using Multipass. The project demonstrates how multiple services can work together with Redis for temporary vote storage, a Worker for asynchronous processing, and PostgreSQL for persistent results.

## ✨ Technologies

- Kubernetes
- Docker
- Node.js
- Redis
- PostgreSQL
- Multipass
- Flannel

## 🚀 Features

- Voting application accessible through Kubernetes NodePort
- Asynchronous vote processing using Redis and Worker
- Persistent result storage with PostgreSQL
- Separate services for voting and results
- Containerized microservices running inside Kubernetes
- Hands-on Kubernetes networking and troubleshooting

## 📌 The Process

I built this project to understand how a real microservices application behaves inside Kubernetes rather than running everything as a single application. The Voting App receives votes and pushes them to Redis, where the Worker processes them asynchronously and stores the results in PostgreSQL. A separate Result App then retrieves and displays the processed results.

While deploying the project, I also worked through practical Kubernetes challenges including ARM image compatibility, pod scheduling, YAML configuration issues, Flannel networking, and accessing NodePort services from outside the cluster.

## 🟢 Running the Project

Deploy the components in the following order:

```bash

kubectl apply -f redis/
kubectl apply -f postgres/
kubectl apply -f voting-app/
kubectl apply -f worker/
kubectl apply -f result-app/
Check the running resources:
kubectl get pods
kubectl get svc
Once everything is running, access the applications using your Multipass VM IP:
Voting App  → http://<VM_IP>:30004
Result App  → http://<VM_IP>:30005


Add your Voting App, Result App, and Kubernetes screenshots here.
🔮 What's Next?
I plan to take this project further by replacing NodePort with Ingress, adding persistent volumes for PostgreSQL, introducing CI/CD automation, and integrating Prometheus and Grafana for monitoring.


📸 Preview
https://github.com/user-attachments/assets/c97072fa-a91c-4724-b691-27284d6ed98b
