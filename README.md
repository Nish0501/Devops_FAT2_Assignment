DevOps Assignment – Dockerfile & Basic Linux Commands​

1. Key DevOps Concepts
CI/CD (Continuous Integration & Continuous Deployment)
A workflow where every code change is automatically built, tested, and deployed, so new features and fixes reach users faster with fewer manual steps. This reduces deployment errors and makes releases more frequent and reliable.​

Infrastructure as Code (IaC)
Instead of configuring servers manually, IaC uses code files to define and manage infrastructure such as servers, networks, and databases. Tools like Terraform and Ansible help automate entire environments so they can be recreated consistently anytime.​

Containerization
Containerization packages an application with its libraries and dependencies into a container image so it runs the same in development, testing, and production. Docker is a popular tool for this, using Dockerfiles to define everything needed for the runtime environment.​

Version Control (Git)
Git tracks every change in project files, lets developers work on branches, and makes it easy to collaborate and roll back if something breaks. This history helps teams understand who changed what and when, which is essential for modern DevOps workflows.​

Automation
Automation removes repetitive manual tasks like building, testing, and deploying by using scripts, pipelines, and tools. This speeds up delivery, reduces human error, and makes processes more predictable.​

2. Steps I Followed to Complete the Assignment
Step 1: Writing the Dockerfile
I created a Dockerfile using Ubuntu as the base image, then installed basic Linux tools and added a shell script to run multiple commands when the container starts.​

text
FROM ubuntu:latest

RUN apt-get update && apt-get install -y \
    tree \
    procps && apt-get clean

COPY commands.sh /commands.sh
RUN chmod +x /commands.sh

CMD ["/bin/bash", "/commands.sh"]
Step 2: Creating the commands.sh Script
This script prints useful system information using basic Linux commands inside the container.​

bash
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
Step 3: Building the Docker Image
I built the Docker image from the Dockerfile in the current directory and tagged it as my-linux-commands.​

text
docker build -t my-linux-commands .
Step 4: Running the Docker Container
I ran a container from the image so the script executes and shows the Linux command outputs.​

text
docker run -it my-linux-commands
Step 5: Initializing a Git Repository
I initialized a local Git repository, added all project files, and created the first commit.​

text
git init
git add .
git commit -m "Initial commit with Dockerfile and shell script"
Step 6: Uploading Project to GitHub
I linked the local repository to a GitHub remote and pushed the code to the main branch.​

text
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main
3. What I Learned From This Assignment
DevOps Concepts
Using Docker and shell scripting showed how automation, consistency, and isolated environments are central to DevOps practices. It also connected theory (CI/CD, IaC, containerization) with a small hands-on example.​

Linux Skills
Running commands inside a container helped in understanding filesystem layout, process listing, and disk usage on Linux. Writing the script also strengthened basic shell scripting skills.​

Git Version Control
Using Git for this mini-project demonstrated how to structure commits, connect to a remote, and maintain a clean history. This mirrors how real DevOps projects are managed in teams.​

Docker Fundamentals
By writing a Dockerfile, building an image, and running a container, it became clear how containerization simplifies setup and makes environments reproducible. This is a key building block before moving into full CI/CD pipelines with Docker images.
