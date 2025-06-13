---
layout: post
title: "Getting Started with Kubernetes: A Beginner's Guide"
date: 2024-01-20 14:30:00 +0800
categories: [kubernetes, devops]
tags: [kubernetes, containers, orchestration, tutorial]
author: aaluopy
---

# Getting Started with Kubernetes: A Beginner's Guide

Kubernetes has become the de facto standard for container orchestration, but getting started can feel overwhelming. In this guide, I'll walk you through the fundamentals and help you understand why Kubernetes is such a game-changer.

## What is Kubernetes?

Kubernetes (often abbreviated as K8s) is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications.

### Key Benefits

- **Scalability**: Automatically scale applications based on demand
- **High Availability**: Ensure applications remain available even when nodes fail
- **Resource Efficiency**: Optimize resource utilization across your cluster
- **Declarative Configuration**: Define desired state and let Kubernetes maintain it

## Core Concepts

### Pods
The smallest deployable unit in Kubernetes. A pod can contain one or more containers that share storage and network.

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-app
spec:
  containers:
  - name: app-container
    image: nginx:1.21
    ports:
    - containerPort: 80
```

### Deployments
Manage the lifecycle of pods, providing features like rolling updates and rollbacks.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.21
        ports:
        - containerPort: 80
```

### Services
Provide stable network endpoints for accessing pods.

```yaml
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  selector:
    app: nginx
  ports:
  - port: 80
    targetPort: 80
  type: ClusterIP
```

## Setting Up Your First Cluster

### Option 1: Minikube (Local Development)

```bash
# Install minikube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

# Start cluster
minikube start

# Verify installation
kubectl cluster-info
```

### Option 2: Kind (Kubernetes in Docker)

```bash
# Install kind
go install sigs.k8s.io/kind@v0.20.0

# Create cluster
kind create cluster --name my-cluster

# Set kubectl context
kubectl cluster-info --context kind-my-cluster
```

## Your First Application

Let's deploy a simple web application:

### Step 1: Create the Deployment

```bash
kubectl create deployment hello-world --image=gcr.io/google-samples/hello-app:1.0
```

### Step 2: Expose the Application

```bash
kubectl expose deployment hello-world --type=LoadBalancer --port=8080
```

### Step 3: Access the Application

```bash
# Get service details
kubectl get services

# For minikube, get the URL
minikube service hello-world --url
```

## Essential kubectl Commands

### Viewing Resources

```bash
# List all pods
kubectl get pods

# List all services
kubectl get services

# Get detailed information
kubectl describe pod <pod-name>

# View logs
kubectl logs <pod-name>
```

### Managing Applications

```bash
# Scale deployment
kubectl scale deployment hello-world --replicas=3

# Update image
kubectl set image deployment/hello-world hello-app=gcr.io/google-samples/hello-app:2.0

# Check rollout status
kubectl rollout status deployment/hello-world

# Rollback if needed
kubectl rollout undo deployment/hello-world
```

## Best Practices for Beginners

### 1. Use Namespaces
Organize resources using namespaces:

```bash
# Create namespace
kubectl create namespace my-app

# Deploy to specific namespace
kubectl apply -f deployment.yaml -n my-app
```

### 2. Set Resource Limits
Always define resource requests and limits:

```yaml
resources:
  requests:
    memory: "64Mi"
    cpu: "250m"
  limits:
    memory: "128Mi"
    cpu: "500m"
```

### 3. Use Health Checks
Implement liveness and readiness probes:

```yaml
livenessProbe:
  httpGet:
    path: /health
    port: 8080
  initialDelaySeconds: 30
  periodSeconds: 10

readinessProbe:
  httpGet:
    path: /ready
    port: 8080
  initialDelaySeconds: 5
  periodSeconds: 5
```

### 4. Use ConfigMaps and Secrets
Externalize configuration:

```bash
# Create ConfigMap
kubectl create configmap app-config --from-literal=database_url=postgres://localhost:5432

# Create Secret
kubectl create secret generic app-secret --from-literal=api_key=your-secret-key
```

## Common Troubleshooting

### Pod Not Starting

```bash
# Check pod status
kubectl get pods

# Get detailed information
kubectl describe pod <pod-name>

# Check logs
kubectl logs <pod-name>
```

### Service Not Accessible

```bash
# Check service endpoints
kubectl get endpoints

# Verify service configuration
kubectl describe service <service-name>

# Test connectivity from within cluster
kubectl run test-pod --image=busybox -it --rm -- wget -qO- http://service-name:port
```

## Next Steps

Now that you have the basics down, consider exploring:

1. **Helm** - Package manager for Kubernetes
2. **Ingress Controllers** - Advanced traffic routing
3. **Persistent Volumes** - Data persistence
4. **RBAC** - Role-based access control
5. **Monitoring** - Prometheus and Grafana integration

## Conclusion

Kubernetes might seem complex at first, but understanding these core concepts will give you a solid foundation. Start small, experiment with local clusters, and gradually work your way up to more complex scenarios.

Remember: the key to mastering Kubernetes is hands-on practice. Don't be afraid to break things – that's how you learn!

---

*In the next post, we'll dive deeper into Kubernetes networking and explore how services, ingress, and network policies work together to provide secure and efficient communication between your applications.*