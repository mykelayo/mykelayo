# Hi, I'm Michael Bello

**Cloud & DevOps Engineer**

> Passionate about infrastructure as code (IaC), CI/CD automation, and cloud-native architectures (AWS/​Azure).

---
## Skills

- **CI/CD & GitOps:** Jenkins, GitHub Actions, ArgoCD, GitOps workflows
- **Infrastructure as Code:** Terraform, AWS CloudFormation
- **Containers & Orchestration:** Docker, Kubernetes (EKS), Helm, Kustomize
- **Cloud Platforms:** AWS (VPC, EC2, EKS, ECR, S3), Azure (VNet, NSGs), OCI
- **Observability:** Prometheus, Grafana, Loki, Promtail, ELK Stack
- **Automation & Scripting:** Python, Bash, Ansible
- **Version Control:** Git (GitHub, branching strategies, CI integration)
- **Additional Skills:** Technical documentation, root cause analysis, project coordination, cross-functional collaboration

---

## Featured Projects

### Real-Time Event-Driven Microservices Platform
*Terraform | AWS EKS | Kubernetes | Apache Kafka (Strimzi) | ArgoCD | GitHub Actions | Python (Flask) | Node.js | Prometheus | Grafana | Loki*

**Event streaming platform with full GitOps automation and observability**
- **Infrastructure**: Provisioned AWS EKS cluster (Kubernetes 1.32) across multi-AZ private subnets with NAT gateway egress using modular Terraform (VPC, EKS, ECR, RDS PostgreSQL, Redis, Kafka, monitoring — 8 modules); resolved plan-time dependency in terraform-aws-modules/eks v21 by staging the apply sequence
- **Microservices**: Architected 4 services — Flask API gateway, Kafka event producer, Python stream processor, Node.js WebSocket server — for real-time event handling
- **CI/CD & GitOps**: Built complete pipeline: GitHub Actions builds → Trivy security scans → SHA-pinned immutable tags to ECR → commits Kustomize manifests → ArgoCD auto-syncs; configured OIDC federation with AWS IAM (no long-lived secrets)
- **Kafka**: Deployed Strimzi 0.43.0 operator in KRaft mode; resolved Helm state bug (orphaned RoleBindings) by installing operator via kubectl and managing only CRD resources through Terraform
- **Container Optimization**: Resolved image availability issues — redirected Bitnami Redis to ECR Public Gallery (Docker Hub prunes old tags; ECR Public has no pull limits within AWS)
- **Observability**: Deployed kube-prometheus-stack (Prometheus + Grafana) with Loki for log aggregation; Prometheus auto-discovers ServiceMonitor resources across all namespaces

**Impact**: Fully automated, zero-touch event platform with immutable image tagging, comprehensive security scanning, and end-to-end observability — entire cluster state driven solely by Git commits

---

### Kubernetes DevOps Platform
*Terraform | AWS EKS | Docker | Kubernetes | ArgoCD | Prometheus | Grafana | Loki*

**Complete DevOps platform with GitOps and full observability**
- **Infrastructure**: Provisioned AWS EKS cluster using reusable Terraform modules (VPC, EKS, ECR, IAM)
- **CI/CD**: Built 4-stage GitHub Actions pipeline (lint → security scan → manifest validation → build/push)
- **GitOps**: Implemented ArgoCD for automated cluster state management
- **Observability**: Deployed Prometheus + Grafana (metrics) and Loki + Promtail (logs)
- **Security**: Designed zero-trust Network Policies and HPA for autoscaling

**Impact**: Reduced deployment time by 70%, cluster setup from days to 15 minutes

---

<div align="center">  
  **"Infrastructure as Code is not just a practice, it's a mindset."**
</div>
