![WhatsApp Image 2025-09-22 at 11 00 17 PM](https://github.com/user-attachments/assets/bd320ae0-8e4e-4afc-ab90-e654a1ea173a)# Kubernetes-3-tier-app
🚀 3-Tier Application Deployment on Kubernetes

This project demonstrates the deployment of a 3-tier application (Frontend + Backend + Database) on Kubernetes using ConfigMaps, Secrets, Persistent Volumes, and Ingress.

📂 Project Structure

The deployment is organized into the following Kubernetes manifest files:

namespace.yaml → Defines a separate namespace for isolation.

configmap.yaml → Stores environment variables/config for the app.

mysql-configmap.yaml → Stores MySQL DB-related configuration.

secret.yaml → Stores sensitive credentials (DB password, etc.).

pvc.yaml → Defines Persistent Volume Claims for database storage.

deployment-frontend.yaml → Deploys the frontend application.

deployment-backend.yaml → Deploys the backend application.

service-frontend.yaml → Exposes frontend deployment internally.

service-backend.yaml → Exposes backend deployment internally.

ingress.yaml → Configures external access to the frontend via domain/URL.

⚙️ Prerequisites

####Kubernetes cluster (Minikube)

Minikube installation:curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

####kubectl CLI configured to access the cluster

Kubectl installation:curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

connection tracking:sudo apt install -y conntrack(Ingress Controller (NGINX, Traefik) sends traffic to services.

For successful routing, connection tracking is required to maintain state of sessions and forward packets correctly.)

####Ingress Controller installed (e.g., NGINX Ingress Controller)
Using kubectl:kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.14.0/deploy/static/provider/cloud/deploy.yaml
for minikube local cluster :minikube addons enable ingress.





