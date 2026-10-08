# Cloud / DevOps Career Roadmap — Fresher to Job-Ready
### Personalized for: Complete beginner | ~10-15 hrs/week | AWS-first track
### Estimated timeline: 7-9 months to interview-ready

---

## How to use this roadmap
Each phase has: **what to learn**, **free resources**, **hands-on task** (non-negotiable — don't skip these), and a **milestone** that proves you actually learned it. Don't move to the next phase until you can *demo* the milestone, not just describe it.

Recruiters in this field don't care how many videos you watched. They care whether you can SSH into a broken server and fix it, or explain why your pipeline failed. So the hands-on tasks matter more than the theory.

---

## Phase 0 — Quick Win (Do this in the next 2 days)
Before diving into fundamentals, get one real thing running in the cloud. This is your motivation anchor for the next 9 months.

**Task:** Launch an AWS EC2 instance and serve a live webpage from it.
(Full step-by-step is below in this chat — go do it today.)

**Milestone:** A public URL (your EC2 public IP) that loads a webpage you set up yourself.

---

## Phase 1 — Linux & Networking Foundations (Weeks 1-4)
**Learn:**
- Linux file system, permissions (chmod/chown), users & groups, processes, package managers (apt/yum)
- Shell navigation: `cd`, `ls`, `grep`, `find`, `ps`, `top`, `systemctl`, log files in `/var/log`
- Networking basics: IP addressing, subnets, DNS, TCP vs UDP, HTTP/HTTPS, ports, firewalls, SSH

**Free resources:** Linux Journey (linuxjourney.com), KodeKloud's free Linux basics course, freeCodeCamp's Linux YouTube course

**Hands-on:** Use your Phase 0 EC2 box (or install Ubuntu via VirtualBox/WSL2). Complete 15-20 real terminal exercises: create users, set permissions, find a process eating CPU, check disk space, tail a log file, set up a cron job.

**Milestone:** You can SSH into any Linux box and diagnose "why is this slow / why did this fail" without Googling every single command.

---

## Phase 2 — Git & Scripting (Weeks 5-7)
**Learn:**
- Git: init, commit, branch, merge, resolve conflicts, GitHub PRs
- Bash scripting: variables, loops, conditionals, functions
- Python basics: syntax, functions, file I/O, working with `boto3` (AWS's Python SDK) — enough for automation, not full software engineering

**Hands-on:** Write and push to GitHub:
1. A bash script that backs up a folder and rotates old backups
2. A bash script that checks disk/CPU/memory and emails/logs an alert if thresholds are crossed
3. A Python script using `boto3` that lists all your S3 buckets or EC2 instances

**Milestone:** A public GitHub repo with clean, working scripts and a proper README.

---

## Phase 3 — AWS Cloud Fundamentals (Weeks 8-12)
**Learn core services:** IAM, EC2, S3, VPC (subnets, route tables, security groups), RDS, Route 53, Elastic Load Balancer, CloudWatch, Lambda basics

**Certification target:** AWS Certified Cloud Practitioner — entry-level, builds resume credibility fast, and forces structured coverage of the fundamentals.

**Free resources:** AWS Skill Builder (official, free tier), freeCodeCamp's AWS courses on YouTube

**Hands-on:**
- Build a VPC with public/private subnets manually via the console — then tear it down and recreate it using AWS CLI
- Host a static website on S3 with proper bucket policies
- Set up IAM users, groups, and least-privilege policies (don't just use root/admin — learn this properly, it's a huge interview topic)

**Milestone:** Pass the Cloud Practitioner exam. Have a VPC architecture diagram (use draw.io or Excalidraw) in your portfolio.

---

## Phase 4 — Docker & Containers (Weeks 13-15)
**Learn:** Images vs containers, Dockerfile syntax, docker-compose, container registries, layers/caching

**Hands-on:** Containerize a simple Python Flask or Node.js app. Push it to Docker Hub AND to AWS ECR. Run it on your EC2 instance.

**Free resources:** Docker official docs, KodeKloud's free Docker course

**Milestone:** A Dockerized app pulled from ECR and running on EC2, with the Dockerfile in your GitHub repo.

---

## Phase 5 — Infrastructure as Code: Terraform (Weeks 16-18)
**Learn:** Providers, resources, state files, variables, modules

**Hands-on:** Rewrite your entire Phase 3 VPC + EC2 setup as Terraform code. Run `terraform destroy` and `terraform apply` to prove it's fully automated and repeatable.

**Free resources:** HashiCorp Learn (free), Terraform AWS provider documentation

**Milestone:** A GitHub repo where your entire infrastructure spins up from one command: `terraform apply`.

---

## Phase 6 — CI/CD Pipelines (Weeks 19-21)
**Learn:** Build/test/deploy stages, triggers, artifacts, secrets management

**Tools:** Start with GitHub Actions (easiest, free), then learn Jenkins basics (still very common in enterprise job postings)

**Hands-on:** Build a pipeline that, on every `git push`:
1. Builds your Docker image
2. Pushes it to ECR
3. Deploys it automatically to your EC2/ECS

**Milestone:** A fully automated pipeline — record a short screen capture of `git push` → live updated app. This is a killer portfolio piece.

---

## Phase 7 — Kubernetes (Weeks 22-25)
**Learn:** Pods, Deployments, Services, Ingress, ConfigMaps/Secrets, `kubectl` basics

**Hands-on:** Use Minikube locally (free, no AWS cost) OR AWS EKS (watch free-tier limits carefully — EKS is not fully free). Deploy your containerized app with proper YAML manifests.

**Free resources:** KodeKloud's Kubernetes course, Kubernetes.io official docs

**Milestone:** App running on a K8s cluster, deployment + service YAML files committed to GitHub.

---

## Phase 8 — Monitoring, Logging & Config Management (Weeks 26-29)
**Learn:** CloudWatch dashboards/alarms, Prometheus + Grafana basics, Ansible playbooks for automated server configuration

**Hands-on:**
- Build a Grafana dashboard showing live metrics from your app
- Write an Ansible playbook that takes a fresh EC2 instance and configures it automatically (installs Docker, sets up users, hardens SSH)

**Milestone:** A monitoring dashboard + an Ansible playbook in your repo.

---

## Phase 9 — Certification Push (Weeks 30-32)
**Target:** AWS Certified Solutions Architect – Associate (most recognized by recruiters after Cloud Practitioner) or study toward AWS Certified SysOps Administrator material even if you delay the exam.

---

## Capstone Portfolio Projects (build these throughout, don't leave for the end)
1. **End-to-end automated deployment** — Terraform + Docker + GitHub Actions + EC2/ECS. One `git push` takes code to a live URL.
2. **Kubernetes microservices demo** — 2-3 small containerized services on EKS/Minikube with monitoring attached.
3. **Infrastructure monitoring dashboard** — CloudWatch/Grafana setup with alerting for a sample production-like environment.

Document each with: a README explaining the "why", an architecture diagram, and a short demo GIF/video. This is what actually gets you shortlisted — not the certifications alone.

---

## Resume, LinkedIn & Job Search (start from Month 3, in parallel)
- **Resume:** Lead with project impact ("automated deployment reducing manual steps from 12 to 1"), not just a list of tool names
- **LinkedIn:** Post your learning progress and project demos regularly — recruiters do search and scroll
- **GitHub:** Pin your 3 capstone repos, keep READMEs clean and screenshot-rich
- **Search these titles:** Cloud Support Engineer, Associate DevOps Engineer, Junior Systems Administrator, Cloud Operations Engineer, L1/L2 Support Engineer (Cloud)
- **Target these employer types:** IT services/MSPs (TCS, Infosys, Wipro, Accenture, Cognizant all run dedicated cloud/DevOps fresher tracks), and startups built natively on AWS

## Interview Prep (Months 7-9)
Master these cold: Linux troubleshooting scenarios, subnetting/DNS resolution flow, AWS core services trade-offs, Docker vs VM, CI/CD pipeline design decisions, Terraform state management, basic K8s architecture.

Be ready to walk through each capstone project on a screen-share and explain **why** you made each decision, not just what you built. Do a few mock interviews before the real ones — I can also role-play as an interviewer with you anytime you want to practice.

---

## Free Resource Stack (bookmark these)
- AWS Skill Builder — official free AWS training
- KodeKloud — free-tier hands-on labs (Linux, Docker, Kubernetes)
- freeCodeCamp YouTube — full-length AWS/DevOps courses
- HashiCorp Learn — Terraform
- Kubernetes.io docs
- Linux Journey (linuxjourney.com)
- GitHub Docs
