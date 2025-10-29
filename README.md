# 🧠 AWS Monitoring Stack — Multi-Node Observability on AWS 🚀

<img width="1470" height="956" alt="Grafana" src="https://github.com/user-attachments/assets/e7dee490-bb3b-467b-be95-ae45ba34b622" />

A full monitoring solution deployed across multiple **RHEL EC2 instances** using **Terraform**, **Ansible**, **Prometheus**, **Node Exporter**, and **Grafana**. This project demonstrates a complete end-to-end DevOps workflow — provisioning infrastructure, automating configuration, deploying monitoring tools, and visualizing performance metrics in real-time.  

---

## ⚙️ Architecture Overview

This setup includes one **main monitoring instance** (running Docker Compose with Prometheus and Grafana) and **five RHEL EC2 nodes** that expose metrics via Node Exporter.  
Prometheus scrapes the metrics from all nodes, and Grafana visualizes them using interactive dashboards.

| Component | Purpose |
|------------|----------|
| **Terraform** | Automated AWS infrastructure creation — VPC, subnets, security groups, and EC2 instances. |
| **Ansible** | Automated remote configuration, Node Exporter installation, and system stress testing. |
| **Docker Compose** | Deployed and managed Prometheus, Grafana, and Node Exporter containers. |
| **Prometheus** | Collected performance data from all monitored instances. |
| **Grafana** | Provided dashboards for CPU, memory, disk, and network metrics visualization. |

---

## 🧩 Infrastructure Setup

Using **Terraform**, the infrastructure was provisioned automatically.  
The configuration included:
- A new **VPC** and subnet.
- A **security group** allowing SSH (22), Grafana (3000), and Prometheus (9090) access.
- Five **RHEL EC2 instances** using AMI `ami-0d67d2fca664feb68`.
- One monitoring instance hosting the Docker-based monitoring stack.



<img width="1470" height="956" alt="For grafana" src="https://github.com/user-attachments/assets/e073538a-df6f-4683-bf40-acaac427a2dc" />



**Key Commands**
```bash



terraform init
terraform plan
terraform apply -auto-approve

Category
Key Takeaway
Terraform (IaC)
Automated multi-node EC2 deployment, resolving IAM and VPC dependencies.
Ansible (Automation)
Configured remote instances seamlessly, proving scalable management.
Docker Compose
Simplified service orchestration for Prometheus, Grafana, and exporters.
Observability
Built a full monitoring pipeline visualizing distributed system performance.
Stress Testing
Generated and analyzed real load metrics in Grafana for system insight.
AWS Networking
Understood VPC, subnet, and security group interactions for cross-node communication.




monitoring-stack/
├── docker-compose.yml
├── prometheus.yml
├── inventory.ini
├── install_node_exporter.yml
├── load-test.yml
├── terraform/
│   ├── main.tf
│   ├── provider.tf
│   └── variables.tf
└── grafana-data/


