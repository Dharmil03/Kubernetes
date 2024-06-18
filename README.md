# Kubernetes Setup with kind, Deployment, and Services

This repository contains configuration files for setting up a Kubernetes cluster using `kind`, and deploying an application with `deployment.yml` and `services.yml`.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [kind](https://kind.sigs.k8s.io/docs/user/quick-start/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

## Steps

### 1. Create a Kind Cluster

First, create a Kubernetes cluster using `kind`. 

```bash
kind create cluster --config kind.yml

### 2. Apply Deployment Configuration


kubectl create deployment example-deployment --image=nginx:latest --replicas=3
kubectl expose deployment example-deployment --port=80 --target-port=80 --name=example-service --type=LoadBalancer

### useful kubectl commands


# Get all resources
kubectl get all

# Describe a specific resource
kubectl describe deployment example-deployment

# Check the logs of a pod
kubectl logs <pod-name>

# Execute a command inside a pod
kubectl exec -it <pod-name> -- /bin/bash

# Delete a specific resource
kubectl delete deployment example-deployment
kubectl delete service example-service


thank youu
