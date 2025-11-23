# DevOps Assignment – Dockerfile + Basic Linux Commands

##  1. Five DevOps Concepts

### *1. CI/CD (Continuous Integration and Continuous Deployment)*
Automatically building, testing, and deploying applications so that new changes reach production faster.

### *2. Infrastructure as Code (IaC)*
Managing servers and infrastructure using code (Terraform, Ansible, etc.) instead of manual configuration.

### *3. Containerization*
Packaging applications and dependencies together in portable containers using Docker.

### *4. Version Control*
Using Git to track changes, collaborate, and maintain the project history.

### *5. Automation*
Reducing manual work by automating builds, tests, deployments, and system setups.

---

##  2. How I Completed This Assignment

### *Step 1: Created Dockerfile*

I created a Dockerfile that uses Ubuntu, installs basic tools, and runs a script containing Linux commands.

### *Step 2: Created commands.sh*

Added basic Linux commands (pwd, ls, df, ps, tree).

### *Step 3: Built the Docker Image*

```sh
docker build -t devops-fat2-shell-cmd  .