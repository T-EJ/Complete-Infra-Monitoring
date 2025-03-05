🚀 Complete Infrastructure Monitoring Using Prometheus and Grafana

📌 Introduction

Infrastructure monitoring is crucial in DevOps for detecting and resolving system issues proactively. This project demonstrates real-world infrastructure monitoring using Prometheus, Grafana, and Loki to dynamically monitor Docker, Kubernetes (AWS EKS), and AWS CloudWatch.

This monitoring stack helps visualize system performance, optimize resource utilization, and ensure high availability.

🎯 Objectives

The main objectives of this project are:

✔️ Setting up Prometheus and Grafana for real-time monitoring.

✔️ Collecting Docker container metrics using cAdvisor.

✔️ Monitoring Kubernetes (AWS EKS) clusters with Prometheus and Grafana.

✔️ Implementing Loki for centralized log monitoring.

✔️ Creating dynamic Grafana dashboards for in-depth visualization.

🛠️ Technologies Used

AWS – Cloud computing platform for infrastructure deployment.

Prometheus – Open-source monitoring system for collecting metrics.

Grafana – Data visualization tool for real-time system monitoring.

Loki – Log aggregation system for efficient log storage and retrieval.

cAdvisor – Container monitoring tool to track resource usage.

⚙️ Setup Guide

📍 Step 1: Prometheus and Grafana Setup on AWS

Deploy Prometheus and Grafana on an AWS EC2 instance.

Configure Prometheus to scrape metrics from multiple sources.

Create Grafana dashboards to visualize system and application metrics.

👉 Installation Guides:

Prometheus Installation & Setup

Grafana Setup

📍 Step 2: Docker Monitoring with cAdvisor

✅ Web Server for Testing:

Deployed a web server to generate HTTP requests and test monitoring.

Verified metrics collection and visualization in Prometheus & Grafana.

✅ Docker Monitoring:

Installed cAdvisor for container performance tracking.

Integrated cAdvisor with Prometheus for real-time metrics collection.

📌 Installation Steps:

sudo apt update && sudo apt install -y docker.io
sudo systemctl start docker && sudo systemctl enable docker
sudo docker run -d --name container1 nginx
sudo docker run -d --name container2 httpd

🚀 Install & Run cAdvisor

sudo docker run -d --name=cadvisor \
  --volume=/:/rootfs:ro \
  --volume=/var/run:/var/run:rw \
  --volume=/sys:/sys:ro \
  --volume=/var/lib/docker/:/var/lib/docker:ro \
  --publish=8080:8080 \
  gcr.io/cadvisor/cadvisor

🎯 Access UI: http://<server-ip>:8080

📍 Step 3: Kubernetes (AWS EKS) Setup & Monitoring

✅ AWS EKS Setup:

Created an Amazon EKS cluster for containerized application deployment.

Installed Prometheus on EKS for cluster health monitoring.

Configured Grafana dashboards for Kubernetes metrics.

📌 Kubernetes Monitoring Setup:

kubectl create namespace monitoring
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
helm install prometheus prometheus-community/prometheus \
  --set alertmanager.persistentVolume.enabled=false \
  --set server.persistentVolume.enabled=false \
  --set server.service.type=NodePort \
  --set server.service.nodePort=30090 -n monitoring

✅ Import Grafana Dashboards:

Kubernetes Cluster Monitoring Dashboard IDs: 15760 & 15759

📊 Real-Time Monitoring with Grafana Dashboards

✔️ Monitor Docker container CPU, memory, disk, and network usage.✔️ Visualize Kubernetes cluster health and performance metrics.✔️ Detect anomalies and optimize system performance proactively.

🎯 Conclusion

This project provides a complete infrastructure monitoring solution using Prometheus and Grafana, covering:
✅ Docker container monitoring with cAdvisor.✅ Kubernetes (AWS EKS) cluster monitoring.✅ Loki for centralized log monitoring.

With dynamic Grafana dashboards, this setup enables real-time monitoring, early issue detection, and system performance optimization. 🚀

🌟 Want to Contribute?

Feel free to fork this repository, submit pull requests, or open issues!

📩 Have Questions? Reach out to me!
Happy Monitoring! 🎯
