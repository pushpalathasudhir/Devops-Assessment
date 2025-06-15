This repository contains the complete DevOps pipeline to deploy a simple Ruby on Rails application with a PostgreSQL database using Docker, Kubernetes, ArgoCD (GitOps), and Tekton CI/CD.
Dockerfile: Builds a basic Ruby on Rails app image with PostgreSQL client.
docker-compose.yml: Spins up a web container and a PostgreSQL DB for local development.
Kubernetes Setup Rails app is deployed via a Deployment and exposed with a Service.
PostgreSQL is deployed using a StatefulSet and exposed with its own Service.
Ingress is used to route external traffic to the Rails service.

ArgoCD GitOps:application.yaml defines how ArgoCD should track and deploy this app from the Git repo.
Includes ArgoCD config files. 
Tekton CI/CD
Pipeline pulls the code, builds a Docker image using Kaniko, and pushes it to Docker Hub.
Files include reusable Tekton Tasks
Application listens on 0.0.0.0:3000
