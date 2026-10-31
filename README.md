# 🏠 Homelab Setup

Production Kubernetes homelab powered by ArgoCD – YAML manifests for daily apps, monitoring, automation and backups

[![GitHub stars](https://img.shields.io/github/stars/kjedynak00/Home-lab?style=social)](https://github.com/kjedynak00/Home-lab)
[![ArgoCD Ready](https://img.shields.io/badge/ArgoCD-Ready-green)](https://argo-cd.readthedocs.io)
![Proxmox](https://img.shields.io/badge/Proxmox-VE-orange)
![Kubernetes](https://img.shields.io/badge/Kubernetes-k3s-blue)
![Maintenance](https://img.shields.io/badge/Maintained-Yes-brightgreen)


---
## 🚀 Description
Personal homelab infrastructure built with Proxmox + Kubernetes (k3s) + ArgoCD (GitOps approach).  
Includes daily-use applications, monitoring with Beszel, workflow automation with n8n and automated nightly backups to a NAS.

---
## 🧱 Stack

Layer | Tool |
| :--- | :--- |
| **Virtualization** | Proxmox VE |
| **Kubernetes** | k3s (control plane on a Proxmox VM + bare-metal worker) |
| **GitOps** | ArgoCD – every app is synced from this repository |
| **Storage** | Longhorn (replicated volumes) + Synology NAS over NFS |
| **Ingress** | Traefik |
| **External access** | Cloudflare Tunnel + Cloudflare Access (no open ports on the router) |
| **Monitoring** | Beszel – CPU, RAM, disks, temperatures and S.M.A.R.T. disk health |

---
## ✨ App Dashboard

Name | What it is doing | Status |
| :--- | :--- | :--- |
| **Kavita** | Self-hosted digital library | 🟢 Production |
| **Mealie** | Recipe management application | 🟢 Production |
| **Beszel** | Lightweight monitoring tool with S.M.A.R.T. disk health | 🟢 Production |
| **n8n** | Workflow automation / low-code pipelines | 🟢 Production |
| **Vaultwarden** | Lightweight password manager (Bitwarden server) | 🟢 Production |
| **Roampage** | Dashboard / landing page with health checks and service management | 🟢 Production |
| **Firefly III** | Self-hosted personal finance and budgeting manager | 🟢 Production |
| **Docmost** | Collaborative wiki and documentation | 🟢 Production |
| **BentoPDF** | Self-hosted PDF toolkit | 🟢 Production |
| **Adguard** | Network-wide ad and tracker blocking with DNS-level protection | ⚪ Testing |
| **Homepage** | Dashboard / landing page | ⚪ Inactive |
| **Wordpress + mariadb + phpmyadmin** | CMS with database stack | ⚪ Inactive |
| **Ollama + open web UI** | Local AI stack with web interface | ⚪ Inactive |
| **qBittorrent** | Torrent client with web UI | ⚪ Inactive |
| **Syncthing** | Continuous file synchronization | ⚪ Inactive |

---
## 🤖 Automation
- **Discord → Firefly III bot (n8n)** – add expenses straight from a Discord channel (`12,50 transport taxi`), with category validation and error replies
- **Bot commands** – `!ile` (spending this month), `!kategorie` (available categories), `!cofnij` (undo the last expense added by the bot), `!help`
- **Monthly summary** – on the 1st of every month: spending per category compared with the previous month, sent to Discord
- **Heartbeat monitoring** – Beszel pings healthchecks.io, so an outage of the monitoring itself is also noticed

---
## 💾 Backups
Defined in [`backups/backups.yaml`](backups/backups.yaml) and synced by ArgoCD:

What | When | Retention |
| :--- | :--- | :--- |
| **Longhorn volumes** (all apps) → NAS | Daily at 03:00 | 7 backups |
| **Postgres dumps** (Firefly, n8n, Docmost) → NAS as `.sql.gz` | Daily at 03:30 | 14 days |

---
## 🔐 Security
- No secrets in this repository – passwords and tokens live in Kubernetes Secrets created by hand and are referenced via `secretKeyRef`
- All web apps are published through Cloudflare Tunnel and protected by Cloudflare Access
- HTTPS enforced everywhere
- Vaultwarden runs with sign-ups and invitations disabled

---
## 📂 Repository Structure
```
Home-lab/
├── apps/       # one folder per application (Deployment, Service, Ingress, PVC...)
└── backups/    # Longhorn recurring backup + nightly Postgres dumps
```

---
## 🛠️ Infrastructure Specs
Role | Hardware | Specs |
| :--- | :--- | :--- |
| **Main Server** | Fujitsu Esprimo Q957 | Intel i5-7500T, 32 GB RAM – Proxmox VE, K8s master as a VM |
| **Worker Node** | Fujitsu Esprimo Q957 | Intel i5-7500T – bare-metal K8s worker |
| **Storage NAS** | Synology 213J | NAS storage (NFS) for app data and backups |

---
## 📌 Notes
- GitOps managed via ArgoCD
- Modular YAML manifests for easy expansion
- Designed for learning, experimentation, and production-like workloads
- New services are continuously being added
---
## 👋 Contact
 - Author: Kacper Jedynak
 - E-mail: [kacperjedynak00@gmail.com](mailto:kacperjedynak00@gmail.com)
 - Linkedin: [My Profile](https://www.linkedin.com/in/kacper-jedynak/)
