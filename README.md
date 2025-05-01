
![image](https://github.com/user-attachments/assets/649fcf39-c210-4b88-a16f-480215587f92)

# GitLab Evaluation Documentation


| Author        | Date       | Version | Review Level   | Reviewer Name        |
|---------------|------------|---------|----------------|----------------------|
| pravalika Kanikarapu  |    | v1.0    | Pre-Reviewer   | Priyanshu            |
| pravalika Kanikarapu  |    |     | L0             | priyanka      |
| pravalika Kanikarapu  |            |         | L1             | Rishabh Sharma       |
| pravalika Kanikarapu  |            |         | L2             | piyush Upadhyay      |

# Table of contents

- [Introduction](#introduction)
- [Purposes](#purposes)
- [Key Features](#key-features)
- [Getting Started](#getting-started)
- [Pre-requisites](#pre-requisites)
- [Software Overview](#software-overview)
- [System Requirements](#system-requirements)
- [Important Ports](#important-ports)
- [Dependencies](#dependencies)
- [Run-time Dependency](#run-time-dependency)
- [Other Dependencies](#other-dependencies)
- [How to Setup/Install GitLab](#how-to-setupinstall-gitlab)
- [Configuration](#configuration)
- [Maintenance](#maintenance)
- [Monitoring](#monitoring)
- [Disaster Recovery](#disaster-recovery)
- [High Availability](#high-availability)
- [Troubleshooting](#troubleshooting)
- [FAQs](#faqs)
- [Contact Information](#contact-information)
- [References](#references)




# Introduction
This document evaluates GitLab, a comprehensive DevOps platform that provides version control, CI/CD (Continuous Integration and Continuous Delivery), issue tracking, and collaborative features, among other functionalities. GitLab allows teams to plan, build, test, deploy, and monitor their applications in a single interface, promoting efficiency in the software development lifecycle.

# Purposes
GitLab can be applied in various scenarios, including:
- **Version Control:** GitLab allows teams to manage their code repositories using Git, making it easier to collaborate and maintain code history.
- **CI/CD Pipelines:** GitLab’s integrated CI/CD system automates the build, test, and deployment process, reducing manual efforts and increasing reliability.
- **Collaboration & Code Review:** The platform provides tools for code reviews, issue tracking, and merge requests, ensuring that teams work together seamlessly.
- **DevOps Automation:** GitLab automates repetitive tasks, such as code deployment and testing, enabling faster and more reliable software delivery.

# Key Features
- **Integrated CI/CD:** GitLab includes built-in pipelines for CI/CD, eliminating the need for external tools.
- **Version Control (Git-based):** GitLab uses Git as its version control system for managing code repositories.
- **Auto DevOps:** GitLab offers Auto DevOps to automatically set up CI/CD pipelines based on best practices.
- **Issue Tracking:** GitLab offers a comprehensive issue tracking system to manage bugs, feature requests, and tasks.
- **Security and Compliance:** GitLab integrates security tools like SAST (Static Application Security Testing), DAST (Dynamic Application Security Testing), and dependency scanning.
- **Container Registry & Kubernetes Integration:** GitLab supports containerized applications with its built-in container registry and native Kubernetes integration for deployment.

# Getting Started

# Pre-requisites

| **Category**        | **Details**                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| **License Type**     | **Commercial Use**: Yes, GitLab offers both free and paid versions with varying features. |
|                     | **Open Source**: Yes, GitLab is open-source, with a robust community edition available. |

# Software Overview

| **Attribute**        | **Details**                                                             |
|----------------------|-------------------------------------------------------------------------|
| **Software**         | GitLab                                                                  |
| **Version**          | 15.10 (or latest stable release)                                        |

# System Requirements

| Requirement          | Minimum                   | Recommendation             |
|----------------------|---------------------------|----------------------------|
| Processor/Instance   | Dual-Core                  | 2 vCPU or higher           |
| RAM                  | 4 GB                       | 8 GB or higher             |
| ROM (Disk Space)     | 10 GB                      | 20 GB or higher            |
| OS Required          | Linux (Ubuntu/Debian)      | Ubuntu 20.04 or later      |

# Important Ports

| Ports | Description |
|-------|-------------|
| 22    | Port 22 is used to establish an SSH connection for remote access to GitLab server. |
| 443   | Standard port for HTTPS communication between client and GitLab server. |
| 80    | HTTP (optional, used if HTTPS is not set up). |

# Dependencies

### Run-time Dependency

| Run-time Dependency | Version   | Description |
|---------------------|-----------|-------------|
| Ruby                | 3.x       | Required for GitLab's backend. |
| PostgreSQL          | 13.x      | GitLab uses PostgreSQL for database management. |

### Other Dependencies

| Other Dependency    | Version   | Description |
|---------------------|-----------|-------------|
| Redis               | 6.x       | Required for caching and background job processing. |
| Git                 | 2.x       | Version control system used by GitLab. |


# How to Setup/Install GitLab

1. **Install Dependencies:** Ensure the system meets the prerequisites (e.g., Ruby, PostgreSQL, Redis).
2. **Download GitLab:** 
   ```bash
   wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh
   sudo bash script.deb.sh
   sudo apt-get install gitlab-ce
   ```

3. **Configure GitLab:** Edit the GitLab configuration file:

   
   ```bash
   sudo nano /etc/gitlab/gitlab.rb
   ```

   Change settings such as external URL and email configuration.

4. **Reconfigure and Start GitLab:**

   ```bash
   sudo gitlab-ctl reconfigure
   sudo gitlab-ctl start
   ```

# Configuration

Configuration involves setting up the GitLab instance to meet specific needs, such as configuring external URLs, database connections, email settings, and more. This can be done through the gitlab.rb configuration file, which is located at /etc/gitlab/gitlab.rb.

# Maintenance

| Task              | Command                                                      | Description                                    |
|-------------------|--------------------------------------------------------------|------------------------------------------------|
| Update GitLab     | `sudo apt-get update && sudo apt-get upgrade gitlab-ce`      | Updates GitLab packages to the latest version. |
| Upgrade GitLab    | `sudo apt-get dist-upgrade`                                   | Performs a full upgrade of the GitLab instance.|
| Restart GitLab    | `sudo gitlab-ctl restart`                                     | Restarts all GitLab services.                 |

---

# Monitoring

| Task                      | Command                          | Description                                                  |
|---------------------------|----------------------------------|--------------------------------------------------------------|
| Check GitLab Status       | `sudo gitlab-ctl status`         | Displays the status of all GitLab components.                |
| View GitLab Logs          | `sudo gitlab-ctl tail`           | Real-time view of logs from all components.                  |
| Monitor Specific Services | `sudo gitlab-ctl tail <service>` | View logs for a specific service (e.g., `gitlab-rails`).     |

---

# Disaster Recovery

| Task             | Command                                                              | Description                                                 |
|------------------|----------------------------------------------------------------------|-------------------------------------------------------------|
| Backup GitLab    | `sudo gitlab-rake gitlab:backup:create`                              | Creates a full backup of GitLab (repositories, DB, uploads).|
| Restore Backup   | `sudo gitlab-rake gitlab:backup:restore BACKUP=timestamp_of_backup` | Restores GitLab data from a backup.                         |
| Schedule Backups | Use cron or systemd timer                                            | Automate regular backups for better resilience.             |

# High Availability

GitLab can be set up in a high-availability configuration by configuring multiple GitLab servers with a load balancer. GitLab supports clustering for better load distribution and uptime.

# Troubleshooting

| Issue                          | Cause                                                              | Solution                                                                                     |
|-------------------------------|---------------------------------------------------------------------|----------------------------------------------------------------------------------------------|
| GitLab won't start            | Misconfigured settings or missing dependencies                     | Check logs: `/var/log/gitlab/gitlab-rails/production.log`; reconfigure using `sudo gitlab-ctl reconfigure`. |
| 502 Gateway Error             | GitLab services not fully started or nginx errors                   | Restart services: `sudo gitlab-ctl restart`; check nginx logs at `/var/log/gitlab/nginx/`.  |
| Database connection failure   | PostgreSQL is down or misconfigured in `gitlab.rb`                 | Ensure PostgreSQL is running; verify credentials and DB host in `/etc/gitlab/gitlab.rb`.    |
| Cannot push to repository     | SSH keys not added or permission issues                            | Add SSH key via GitLab UI; ensure correct repo URL and user permissions.                    |
| CI/CD pipeline not running    | Runner not registered or misconfigured                             | Register a runner using `gitlab-runner register`; check runner status in GitLab UI.         |
| Email not sent                | SMTP settings not configured correctly                             | Verify SMTP settings in `gitlab.rb`; reconfigure and restart GitLab.                        |
| Slow performance              | Insufficient system resources or high load                         | Monitor with `top` or `htop`; upgrade instance specs or tune GitLab settings.               |

# FAQs

**Q: Is GitLab free?**  
Yes, GitLab has an open-source version called GitLab Community Edition (CE), which is free to use. There is also a paid version, GitLab Enterprise Edition (EE), which offers additional features for larger teams and organizations.

**Q: Can GitLab be deployed on any cloud platform?**  
Yes, GitLab can be deployed on all major cloud platforms including AWS, Microsoft Azure, and Google Cloud Platform (GCP).

**Q: Is there an enterprise version of GitLab?**  
Yes, GitLab offers GitLab Enterprise Edition (EE), which includes advanced features such as enhanced security, compliance tools, and support options designed for large organizations.


#  Contact Information


| Name       | Email Address                |
|------------|------------------------------|
| Pravalika  | kanikarapu.pravalika.snaatak@mygurukulam.co|

# References 

| Link | Description |
|------|-------------|
| [Gitlab](https://www.site24x7.com/learn/what-is-gitlab.html) | Documentation followed from this guide |


