DevOps Real-time Project: Swiggy Clone App Deployment

🛠️ Real-Time Food E-Commerce Platform (Swiggy-Clone) – DevOps Automation Pipeline
🚀 Overview

This repository contains the complete implementation of a fully automated CI/CD pipeline for a real-time food-ordering platform inspired by Swiggy.
The project integrates DevOps practices and industry-standard open-source tools to automate code integration, testing, containerization, infrastructure provisioning, deployment, and monitoring on AWS Cloud.

🧩 Key Objectives

Automate the entire code-to-deployment lifecycle using DevOps.

Ensure zero-downtime deployments with Kubernetes rolling updates.

Implement security-focused continuous integration (DevSecOps).

Enable auto-scaling, real-time monitoring, and feedback loops.

Maintain environment consistency through Infrastructure as Code (IaC).

⚙️ Tech Stack

Frontend: ReactJS, HTML, CSS, JavaScript, Bootstrap
Backend: Node.js, Express.js, REST APIs, MongoDB/DynamoDB
DevOps Tools: Jenkins, Docker, Kubernetes, Terraform, Ansible
Security & Quality: SonarQube, OWASP Dependency Check, Trivy
Monitoring & Alerts: Prometheus, Grafana, Slack Integration
Cloud Platform: AWS EC2, EKS, S3, IAM, CloudWatch

🧱 System Architecture

The architecture follows a microservices-based approach, where frontend, backend, and supporting services are containerized and orchestrated through Kubernetes on AWS.
Each commit triggers an automated Jenkins pipeline that validates, builds, and deploys the latest version of the platform.

graph LR
A[GitHub Code Commit] --> B[Jenkins CI Pipeline]
B --> C[SonarQube + Security Scans]
C --> D[Docker Build & Push to DockerHub]
D --> E[Terraform Infrastructure Provisioning]
E --> F[Ansible Configuration Management]
F --> G[Kubernetes Deployment & Autoscaling]
G --> H[Prometheus & Grafana Monitoring]
H --> I[Slack Alerts & Developer Feedback]
I --> A

🔁 CI/CD Pipeline Flow
Stage	Tool(s) Used	Description
1. Code Commit	GitHub	Developers push application and IaC code (ReactJS, Node.js, Terraform, Ansible, Jenkinsfile).
2. CI Trigger	Jenkins	Jenkins (on AWS EC2) detects commits and triggers the pipeline automatically.
3. Code Quality & Security	SonarQube, OWASP, Trivy	Static analysis and vulnerability scans ensure clean and secure builds.
4. Build & Containerization	Docker, DockerHub	Application packaged into Docker images and pushed to DockerHub.
5. Infrastructure Provisioning	Terraform	AWS resources (EC2, Security Groups, Networking) created automatically.
6. Configuration Management	Ansible	Automates installation of Docker, Jenkins agents, and dependencies.
7. Deployment & Scaling	Kubernetes (AWS EKS)	Docker images deployed as pods with rolling updates and autoscaling.
8. Monitoring & Alerts	Prometheus, Grafana, Slack	Real-time health checks, performance dashboards, and instant alerts.
9. Feedback Loop	GitHub, Jenkins	Monitoring insights drive new commits and continuous improvement.
🧰 Repository Structure
├── frontend/                  # ReactJS Frontend Code
├── backend/                   # Node.js API Services
├── Dockerfile                 # Docker build configuration
├── Jenkinsfile                # CI/CD pipeline definition
├── terraform/                 # Terraform scripts for AWS provisioning
│   ├── main.tf
│   ├── variables.tf
│   └── outputs.tf
├── ansible/                   # Ansible playbooks for configuration
│   ├── install_docker.yml
│   ├── setup_jenkins.yml
│   └── deploy_app.yml
├── k8s/                       # Kubernetes deployment manifests
│   ├── deployment.yaml
│   └── service.yaml
├── monitoring/                # Prometheus & Grafana configuration
│   ├── prometheus.yml
│   └── grafana_dashboard.json
└── README.md                  # You are here

⚡ How to Deploy
1️⃣ Clone the Repository
git clone https://github.com/<your-username>/swiggy-devops-pipeline.git
cd swiggy-devops-pipeline

2️⃣ Initialize Terraform and Provision AWS Infrastructure
cd terraform
terraform init
terraform plan
terraform apply -auto-approve

3️⃣ Configure EC2 Instance using Ansible
cd ../ansible
ansible-playbook -i inventory.ini setup_jenkins.yml
ansible-playbook -i inventory.ini install_docker.yml

4️⃣ Run Jenkins Pipeline

Access Jenkins at http://<EC2-Public-IP>:8080

Configure credentials for GitHub, DockerHub, and AWS

Run the pipeline defined in Jenkinsfile

5️⃣ Deploy Application via Kubernetes
cd ../k8s
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

6️⃣ Access Application
http://<LoadBalancer-DNS>:3000

7️⃣ View Monitoring Dashboards

Prometheus: http://<EC2-Public-IP>:9090

Grafana: http://<EC2-Public-IP>:3000

📊 Testing & Validation

Terraform Testing: Verified repeatable infra creation and destruction.

Docker Testing: Validated image integrity and run performance.

Kubernetes Testing: Checked pod autoscaling and rolling updates.

Security Testing: Ensured zero high-severity vulnerabilities through OWASP & Trivy.

Monitoring: Validated real-time metrics and Slack alert delivery.

🧠 Key Learnings

Seamless automation of the complete CI/CD lifecycle on AWS.

Achieved 99.9 % uptime through rolling updates and health checks.

Demonstrated Infrastructure as Code (Terraform) and Configuration as Code (Ansible).

Integrated security scanning (DevSecOps) within the build pipeline.

Established proactive monitoring and rapid feedback loops.

📈 Future Enhancements

Introduce canary or blue-green deployments for safer rollouts.

Integrate HashiCorp Vault for advanced secret management.

Implement AI-driven anomaly detection within Prometheus metrics.

Expand to multi-region deployments using AWS EKS Clusters.

👥 Contributors

Aditya Vikram Singh – CI/CD Pipeline & Infrastructure Automation

Yash Srivastava – Application Development & Deployment

Guide: Dr. V. Deeban Chakravarthy V, Associate Professor, Department of Computing Technologies

🧾 License

This repository is created as part of an academic DevOps project under SRM Institute of Science and Technology.
All rights reserved © 2025.
