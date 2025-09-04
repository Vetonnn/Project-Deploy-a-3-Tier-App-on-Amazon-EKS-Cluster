Deploy a 3-Tier App on Amazon EKS (with CI/CD)


🎯 Learning Goals

Provision a real Kubernetes cluster (EKS) and understand its building blocks (nodegroups, addons).

Package microservices into Docker images and push to a registry.

Deploy with Kubernetes manifests (Deployments, Services, Ingress).

Automate builds & deploys with GitHub Actions (CI/CD).

Troubleshoot cloud quotas, networking (Ingress), and secrets.

🧱 Architecture (3-Tier)

Frontend: vote (Python) + result (Node.js)

Backend/Worker: .NET worker that moves messages from Redis → Postgres

Data: redis (queue) + postgres (persistent DB)

Platform: Amazon EKS (managed Kubernetes)

Traffic: NGINX Ingress (routes /vote and /result)

CI/CD: GitHub Actions → Build → Push → kubectl apply

🧰 Prerequisites

AWS account with EKS permissions (IAM user + access keys)

kubectl, awscli, eksctl installed locally

Docker & a container registry (Docker Hub)

GitHub repo secrets set:

AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, AWS_REGION

DOCKERHUB_USERNAME, DOCKERHUB_TOKEN

(Optional) KUBE_CLUSTER_NAME if referenced in the workflow

📦 Repo Layout (key parts)

vote/, result/, worker/ — app code + Dockerfile per service

K8s/ — Kubernetes manifests (Deployments, Services, Ingress, Secrets refs)

.github/workflows/ — CI/CD pipeline (build images → deploy to EKS)

healthchecks/ — basic health probes / scripts (if used)

docker-compose.yml — local dev/testing
