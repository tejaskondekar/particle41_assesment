---

## Project Structure

- **Flask App**: A Python service that returns the current server time.
- **Docker**: Containerizes the Flask app.
- **Terraform**: Provisions the full infrastructure in AWS.
- **ECS Fargate**: Runs the containerized application securely in private subnets.

---

## Docker Image

The image is available publicly on Docker Hub:

docker pull tejaskondekar1008/simpletimeservice:latest


## Infrastructure Setup Using Terraform

```bash

1. Clone the Repository

```bash

---

git clone https://github.com/your-username/your-repo.git
cd your-repo

---

```bash

2. AWS Credentials

```bash

Make sure you’ve configured your AWS credentials using one of the following:

---

export AWS_ACCESS_KEY_ID=your-access-key
export AWS_SECRET_ACCESS_KEY=your-secrete-key

---

```bash

3.Initialize Terraform, Review the Plan and Apply the Infrastructure

```bash

---

terraform init
terraform plan
terraform apply

---
Approve when prompted (yes).

```bash

4. Access the App

```bash

Once the apply is complete, Terraform will output a DNS name:
---

http://<your-load-balancer-dns>

---

Visit it in your browser to see the Flask time service.


