# 🛠️ Homelab + Ansible Learning Roadmap  

This roadmap gradually introduces **Ansible** and **System Administration principles** so your homelab grows closer to industry standards over time.  

---

## **Stage 1 – Build a Foundation (Current State → Organized Basics)**
**Focus:** Get out of the “root SSH + random playbooks” phase. Learn structure, idempotence, and basic sysadmin hygiene.  

**Goals:**  
- 🔑 **SSH & Access**:  
  - Stop using root SSH. Create a dedicated `ansible` user with sudo privileges.  
  - Push SSH keys to all machines with Ansible (`authorized_keys` module).  

- 📂 **Organize Playbooks**:  
  - Learn folder structure: inventories, group_vars, host_vars.  
  - Split tasks into simple **roles** (e.g., `docker`, `users`, `updates`).  

- 🛡️ **System Hygiene**:  
  - Automate package updates & security patches.  
  - Configure UFW or firewalld via Ansible for basic firewall rules.  

➡️ **Principles learned**: principle of least privilege, configuration management basics, idempotence, repeatability.  

---

## **Stage 2 – Service & Application Automation**
**Focus:** Learn how to manage **services and applications** consistently.  

**Goals:**  
- 📦 **Docker Playbooks**: Move from “update containers” → “define apps as roles.”  
  - Example: A `grafana` role that installs Docker, creates a container, and sets configs.  
- 🌐 **Reverse Proxy**: Deploy Traefik or Nginx Proxy Manager with Let’s Encrypt certs.  
- 👥 **User Management**: Centralize all user creation (you, service accounts, test users).  

➡️ **Principles learned**: application lifecycle management, separation of concerns (roles), reproducible app deployment.  

---

## **Stage 3 – Monitoring & Reliability**
**Focus:** Learn how to **observe and maintain** a healthy environment.  

**Goals:**  
- 📊 Deploy monitoring stack (Prometheus + Node Exporter + Grafana) with Ansible.  
- 📜 Central logging (Loki, or at least rsyslog config).  
- 🔍 Add health checks (e.g., Ansible `uri` to confirm containers are serving HTTP 200).  
- 🌀 Schedule Ansible playbooks with Semaphore or cron for regular maintenance.  

➡️ **Principles learned**: monitoring & observability, proactive operations, continuous compliance.  

---

## **Stage 4 – Infrastructure as Code Maturity**
**Focus:** Make your environment feel like a “mini-enterprise.”  

**Goals:**  
- 🏗️ **Inventory Organization**: Split hosts into groups (`web`, `db`, `infra`, `apps`). Use group_vars to define differences.  
- 🔒 **Secrets Management**: Store app passwords, API tokens, certs in **Ansible Vault**.  
- 🖥️ **Golden Image Role**: Create a base role that configures any new VM with:  
  - Users, SSH, firewall, updates, monitoring agent, Docker.  
- 🚀 **GitOps Workflow**: Tie Ansible repo → Semaphore CI/CD → auto-deploy on Git push.  

➡️ **Principles learned**: standardization, environment consistency, secrets handling, automation pipelines.  

---

## **Stage 5 – Advanced & Interview-Ready Projects**
**Focus:** Show “real-world” problem solving.  

**Goals:**  
- 🔁 **Disaster Recovery Simulation**:  
  - Write a playbook to recreate an app stack (e.g., Nextcloud + DB + Proxy) from scratch on a fresh VM.  
- ☁️ **Hybrid Experiment**: Deploy part of your stack to AWS free tier (EC2 + S3), provision with Ansible.  
- 📦 **Role Publishing**: Take one of your polished roles (e.g., Docker + Traefik), publish it to **Ansible Galaxy**.  
- 🧑‍💻 **Documentation/Portfolio**: Write a README for each role/playbook. Add screenshots of monitoring dashboards, app UIs, architecture diagrams.  

➡️ **Principles learned**: disaster recovery, hybrid/cloud management, community contribution, professional documentation.  

---

# 🗂️ Suggested Timeline
- **Month 1–2:** Stage 1 → 2 (clean up access, organize, start deploying apps properly).  
- **Month 3–4:** Stage 3 (monitoring/logging, health checks).  
- **Month 5–6:** Stage 4 (vault, golden images, GitOps).  
- **Month 6+**: Stage 5 (cloud, recovery, portfolio).  

---

👉 By the end, you’ll have:  
- A homelab that looks and feels like a **mini production environment**.  
- A Git repo with **reusable roles** and IaC workflows.  
- Real “war stories” to tell employers about system management, monitoring, recovery, and automation.  
