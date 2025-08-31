# WP Stack (WordPress + MariaDB, Helm)

Minimal Helm chart to deploy WordPress + MariaDB on Kubernetes (tested on Minikube on EC2).

## Prerequisites
- Kubernetes cluster (e.g., Minikube), `kubectl`, `helm`
- Container images:
  - WordPress: `992382545251.dkr.ecr.us-east-1.amazonaws.com/wordpress-amiel:latest`
  - MariaDB: `992382545251.dkr.ecr.us-east-1.amazonaws.com/mariadb-amiel:10.6.4-focal`

## Install
```bash
cd wp-stack
helm upgrade --install wp .
kubectl get pods -w   # wait until wordpress x2 and mariadb-0 are 1/1 Ready
