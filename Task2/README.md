# Simple Time Service - AWS Fargate Deployment

This project demonstrates how to containerize a Flask app and deploy it on AWS ECS using Terraform.

---

## Project Structure

- **Flask App**: A Python service that returns the current server time.
- **Docker**: Containerizes the Flask app.
- **Terraform**: Provisions the full infrastructure in AWS.
- **ECS Fargate**: Runs the containerized application securely in private subnets.

---

## Docker Image

The Docker image is available publicly on Docker Hub:

```bash
docker pull tejaskondekar1008/simpletimeservice:lates

# Infrastructure Setup Using Terraform
1️⃣ Clone the Repository
bash
Copy
Edit
git clone https://github.com/your-username/your-repo.git
cd your-repo
2️⃣ Configure AWS Credentials
Make sure you’ve configured your AWS credentials using one of the following:

bash
Copy
Edit
export AWS_ACCESS_KEY_ID=your-access-key
export AWS_SECRET_ACCESS_KEY=your-secret-key
Or use the AWS CLI:

bash
Copy
Edit
aws configure
3️⃣ Initialize, Plan, and Apply Terraform Configuration
bash
Copy
Edit
terraform init
terraform plan
terraform apply
Approve with yes when prompted.

4️⃣ Access the App
Once terraform apply is complete, Terraform will output a DNS name:

text
Copy
Edit
http://<your-load-balancer-dns>
Visit it in your browser to see the Flask time service live.

✅ Notes
ECS Tasks are deployed in private subnets

Load Balancer is placed in public subnets

