
# 🗳️ Voting App on Amazon EKS with CI/CD

This project deploys the **classic Voting App** to a Kubernetes cluster on **Amazon EKS**, fully automated with a **CI/CD pipeline** using GitHub Actions and Docker Hub.

---

## 🚀 Project Overview

The Voting App is a microservices application with the following components:

- **Vote (Frontend)** – Python app where users can vote (Cats 🐱 or Dogs 🐶).
- **Result (Frontend)** – Node.js app showing the voting results in real time.
- **Worker (Backend)** – .NET app processing votes from the queue.
- **Redis** – In-memory database used as a queue.
- **Postgres** – Database to persist votes.

---

## 🛠️ Architecture

1. **Infrastructure:** Amazon EKS cluster provisioned and running workloads.  
2. **Networking:** Exposed using **NGINX Ingress** and Route53 DNS.  
3. **CI/CD:** GitHub Actions pipeline builds and pushes Docker images → deploys to Kubernetes automatically.  

