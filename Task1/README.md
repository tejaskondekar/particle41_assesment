# Particle41 Assessment - Simple Time Service

This is a simple Flask-based web server that returns the current timestamp and the IP address of the requester in a pure JSON format. This project demonstrates running the application locally using a virtual environment, containerizing it with Docker, and pushing the Docker image to Docker Hub.

## Requirements

Ensure the following are installed on your Linux EC2 instance:

- Python 3
- Docker
- Git
- `pip` (Python package installer)

## Step-by-Step Setup

### 1. Launch EC2 Instance
- Launch a Linux EC2 instance (Amazon Linux 2 or Ubuntu).
- SSH into the instance.

### 2. Install Python3 and Docker

```bash

# Update package list
sudo apt update && sudo apt upgrade -y

# Install Python3 and pip
sudo apt install python3 python3-pip -y

# Install Docker

sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker

3. Clone the GitHub Repository (After Pushing)

git clone https://github.com/tejaskondekar/particle41_assesment.git
cd particle41_assesment

4. (Optional) Create and Activate Virtual Environment

python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

5. Run Flask App Locally

python app.py
# Visit http://<EC2_PUBLIC_IP>:5000

Docker Instructions
1. Create Dockerfile

# Dockerfile

FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["python", "app.py"]


2. Create requirements.txt

flask

3. Build Docker Image

docker build -t simpletimeservice .

4. Test the Image Locally

docker run -d -p 5000:5000 simpletimeservice

# Visit http://<EC2_PUBLIC_IP>:5000

#Push to Docker Hub

1. Tag and Push Docker Image

docker tag simpletimeservice tejaskondekar1008/simpletimeservice:latest

# Login to Docker

docker login

# Push to Docker Hub

docker push tejaskondekar1008/simpletimeservice:latest

#GitHub Repository

GitHub Repo: particle41_assesment


# Initialize Git (if not already done)

git init
git remote add origin https://github.com/tejaskondekar/particle41_assesment.git

# Add and commit changes

git add .
git commit -m "<Comment>"

# Push code

git branch -M main
git push -u origin main

#Example JSON Response

{
  "timestamp": "2025-07-10T10:30:00Z",
  "ip": "203.0.113.45"
}

# Project Structure

particle41_assesment/
│
├── app.py
├── Dockerfile
├── requirements.txt
└── README.md

#Notes:

Make sure port 5000 is allowed in EC2 security group.

Docker image: tejaskondekar1008/simpletimeservice
