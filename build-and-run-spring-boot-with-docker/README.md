Steps Used

================================================
1. Created 2 Dockfiles 
   1. Spring Boot
   2. Mariadb
2. Created Docker-compose file for redis server
================================================

Commands Used

================================================

Path
Spring_Boot/build-and-run-spring-boot-with-docker/Frontend
docker build -t spring-boot-assignment Dockerfile

================================================

Path
Spring_Boot/build-and-run-spring-boot-with-docker/Backend
docker build -t mariadb Dockerfile

===============================================

Path Spring_Boot/build-and-run-spring-boot-with-docker
docker-compose  up -d

===============================================

Minikube Installed 
# Not using any VM
minikube start \
  --memory 4096 \
  --extra-config=controller-manager.horizontal-pod-autoscaler-upscale-delay=1m \
  --extra-config=controller-manager.horizontal-pod-autoscaler-downscale-delay=2m \
  --extra-config=controller-manager.horizontal-pod-autoscaler-sync-period=10s --vm-driver=none

==================================================

Path

Spring_Boot/build-and-run-spring-boot-with-docker/monitoring

=====================================================

Deploy the Metrics Server in the kube-system namespace:

kubectl create -f monitoring/metrics-server

Create the monitoring namespace

kubectl create -f monitoring/namespaces.yaml

Deploy Prometheus v2 in the monitoring namespace

kubectl create -f monitoring/prometheus

Deploy the Prometheus custom metrics API adapter

kubectl create -f monitoring/custom-metrics-api

=====================================================

Path

Spring_Boot/build-and-run-spring-boot-with-docker/kube

Deploy the application in Kubernetes with:

kubectl create -f kube/deployment

Autoscaling workers

kubectl create -f kube/hpa.yaml

==================================================


