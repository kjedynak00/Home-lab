# 🏠 Homelab Setup

Production Kubernetes homelab powered by ArgoCD – YAML manifests for daily apps + monitoring stack

[![GitHub stars](https://img.shields.io/github/stars/ToxicPL/Home-lab?style=social)](https://github.com/ToxicPL/Home-lab)
[![ArgoCD Ready](https://img.shields.io/badge/ArgoCD-Ready-green)](https://argo-cd.readthedocs.io)
![Proxmox](https://img.shields.io/badge/Proxmox-Cluster-orange)
![Kubernetes](https://img.shields.io/badge/Kubernetes-K8s-blue)
![Maintenance](https://img.shields.io/badge/Maintained-Yes-brightgreen)


---
## 🚀 Description
Personal homelab infrastructure built with Proxmox + Kubernetes + ArgoCD (GitOps approach).  
Includes daily-use applications and a monitoring stack with Grafana, Prometheus, and Beszel.

---


## ✨ App Dashboard

Name | What it is doing | Status |
| :--- | :--- | :--- |
| **Kavita** | Self-hosted digital library | 🟢 Production |
| **Mealie** | Recipe management application   | 🟢 Production |
| **Beszel** | Lightweight monitoring tool  | 🟢 Production |
| **Homepage** | Dashboard / landing page  | 🟡 In Progress |
|  **Wordpress + mariadb + phpmyadmin** | CMS with database stack  | ⚪ Inactive |
| **Ollama + open web UI** | Local AI stack with web interface    | ⚪ Inactive |
| **n8n** | Workflow automation / low-code pipelines | 🟢 Production |
| **Vaultwarden** | Lightweight password manager (Bitwarden server) | 🟢 Production |
| **Roampage** | Dashboard / landing page with health checks and service management | 🟢 Production |
| **Firefly** | Self-hosted personal finance and budgeting manager | 🟢 Production |

---
## 🛠️ Infrastructure Specs
Role | Hardware | Specs |
| :--- | :--- | :--- |
| **Main Server** | Fujitsu Esprimo Q957 | Proxmox + K8s Master Server |
| **Worker Node** | Fujitsu Esprimo Q957 | K8s Worker |
| **Storage NAS** | Synology 213J | Nas storage |

---
## 📌 Notes
- GitOps managed via ArgoCD
- Modular YAML manifests for easy expansion
- Designed for learning, experimentation, and production-like workloads
- New services are continuously being added
---
## 👋Contact 
 - Author: Kacper Jedynak
 - E-mail: [kacperjedynak00@gmail.com](mailto:kacperjedynak00@gmail.com)
 - Linkedin: [My Profile](https://www.linkedin.com/in/kacper-jedynak/)
