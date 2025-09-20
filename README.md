# java1kind_ops.sh

**java1kind_ops.sh** is a **one-of-a-kind, production-grade, secure Bash-native ops utility** designed to enhance modern DevOps workflows across **RHEL, Ansible, Terraform, Vault, Puppet Enterprise, Prometheus, GitLab CI/CD, Azure DevOps, and GitHub Actions**.

This script introduces **atomic deploys**, **AES-256-GCM encrypted backups**, **certificate expiry tracking**, and **health checks**—all in a single-page Bash solution. It is built for **enterprise-grade reliability, concurrency safety, and auditability**.

---

## 🚀 Features
- 🔐 **AES-256-GCM encrypted backups** (OpenSSL-based, secure & portable)
- ⚡ **Atomic deploys** with staging → swap workflow
- 📦 **Ansible integration**: secure atomic deploys with RHEL-native ops
- 🔑 **Terraform/Vault integration**: bolt-on secure backups, policy-aware
- 🛠 **Puppet Enterprise extension**: concurrency-safe encrypted backups
- 📊 **Prometheus metrics output** for auditing & observability
- 🧩 **GitLab CI/CD enhancer**: staging deploys + cert expiry alerts
- ☁️ **Azure DevOps & GitHub integration**: production-ready backups & health checks
- ✅ **Error handling & logging**: resilient against runtime failures
- 🛡 **Security-first design**: complies with cryptographic best practices

---

## 📦 Requirements
- **RHEL 8+ / CentOS / Fedora** (other Linux distros may work with minor adjustments)
- **Bash 5+**
- **OpenSSL 1.1.1+**
- **Prometheus Node Exporter** (optional, for metrics scraping)
- **Ansible / Terraform / Puppet / Vault / GitLab CI/CD / Azure DevOps / GitHub** (optional, bolt-on integrations)

---

## ⚙️ Usage
```bash
# Make executable
chmod +x java1kind_ops.sh

# Show help
./java1kind_ops.sh --help

# Perform an atomic deploy with encrypted backup
./java1kind_ops.sh deploy --src /opt/staging/app --dest /opt/prod/app --backup /secure/backups

# Create encrypted backup only
./java1kind_ops.sh backup --src /etc/ansible --out /secure/backups/ansible.enc

# Health check with Prometheus metrics
./java1kind_ops.sh health --metrics /var/lib/node_exporter/textfile/java1kind_ops.prom

🔒 Security
Uses AES-256-GCM for encryption (modern, authenticated encryption)
Ensures atomicity of deploy operations
Validates inputs, handles concurrency safely
Tracks certificate expiry for proactive ops management
📊 Example Prometheus Metrics
java1kind_ops_backup_last_success{target="ansible"} 1695072345
java1kind_ops_deploy_last_success{target="prod"} 1695072400
java1kind_ops_cert_expiry_days{cert="example.com"} 23
