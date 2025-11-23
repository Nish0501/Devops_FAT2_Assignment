# DevOps Assignment – Dockerfile & Basic Linux Commands

## 1. Key DevOps Concepts (Explained in Simple Words)

### 1. CI/CD (Continuous Integration & Continuous Deployment)
A workflow where every code change is automatically built, tested, and deployed. This speeds up releases and reduces the chances of errors during deployment.

### 2. Infrastructure as Code (IaC)
Instead of configuring servers manually, IaC uses code files to create and manage infrastructure. Tools like Terraform and Ansible help automate entire environments.

### 3. Containerization
This is the process of packaging an application along with all its dependencies into a container. Tools like Docker ensure the application behaves the same in development, testing, and production.

### 4. Version Control (Git)
Git helps track changes in a project, work on different branches, collaborate with teammates, and maintain a full history of modifications.

### 5. Automation
Automation removes repetitive tasks like testing, building, or deployments by using tools, scripts, or pipelines—resulting in faster and error-free workflows.

---

## 2. Steps I Followed to Complete the Assignment

### Step 1: Writing the Dockerfile
I created a Dockerfile using Ubuntu as the base image. Inside the image, I installed some basic Linux tools and included a shell script that runs multiple commands.

**Dockerfile**
FROM ubuntu:latest

RUN apt-get update && apt-get install -y
tree
procps && apt-get clean

COPY commands.sh /commands.sh
RUN chmod +x /commands.sh

CMD ["/bin/bash", "/commands.sh"]

text

### Step 2: Creating the commands.sh Script
This script prints system information using basic Linux commands.

**commands.sh**
#!/bin/bash

echo "Current Directory:"
pwd

echo "Listing Files:"
ls -l

echo "Disk Usage:"
df -h

echo "Running Processes:"
ps aux

echo "Directory Tree:"
tree /

text

### Step 3: Building the Docker Image
docker build -t my-linux-commands .

text

### Step 4: Running the Docker Container
docker run -it my-linux-commands

text

### Step 5: Initializing a Git Repository
git init
git add .
git commit -m "Initial commit with Dockerfile and shell script"

text

### Step 6: Uploading Project to GitHub
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main

text

---

## 3. What I Learned From This Assignment

### DevOps Concepts
Working with Docker and scripting introduced me to automation, consistency, and environment isolation—fundamental ideas in DevOps.

### Linux Skills
Running commands inside a Docker container helped me understand how Linux works, explore system utilities, and practice shell scripting.

### Git Version Control
Using Git taught me how to track changes, create commits, push to a remote repository, and maintain clean project history.

### Docker Fundamentals
By writing a Dockerfile, building an image, and running a container, I learned how containerization simplifies application setup and deployment.
