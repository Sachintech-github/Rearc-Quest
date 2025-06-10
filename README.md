# Rearc Quest Challenge – Full Stack Deployment with Docker, ECS, and Terraform

## 🌐 📸 Proof of Completion

✅ Application live on: https://sachincareer.in.net

✅ Hosted on AWS using ECS Fargate and ALB

✅ Website URL and Screenshots

Website: https://sachincareer.in.net 
ALB DNS: https://quest-alb-216061199.ap-south-1.elb.amazonaws.com/

- All stages from Website: https://snipboard.io/BHFQ3j.jpg
- Health Check: https://snipboard.io/i9rZaB.jpg  -- and -- https://snipboard.io/yQklYU.jpg
- ECS Console: https://snipboard.io/gQi691.jpg  
- ECS Deployment: https://snipboard.io/3GVlwn.jpg
- Service Events: https://snipboard.io/UiDmBn.jpg
- Task: https://snipboard.io/S3Lc9M.jpg
- ELB: https://snipboard.io/eViFsE.jpg -- and -- https://snipboard.io/3TZyH4.jpg
- SSL: https://snipboard.io/YNRImJ.jpg
- ECR Image: https://snipboard.io/vGaeqJ.jpg
- EC2 Instance: https://snipboard.io/GfpQ6k.jpg

## 📦 Project Structure

```/home/quest/
├── Dockerfile
├── README.md
├── bin
│   ├── 001
│   ├── 002
│   ├── 003
│   ├── 004
│   ├── 005
│   └── 006
├── main.tf
├── outputs.tf
├── package.json
├── src
│   └── 000.js
├── terraform.tfstate
├── terraform.tfstate.backup
└── variables.tf```

- Screenshot: https://snipboard.io/RMwiUC.jpg



---

## 🚀 Project Overview

- Docker containerization
- ECS Fargate deployment
- Application Load Balancer (ALB) routing
- Target groups with health checks
- TLS termination using HTTPS listener
- Full Infrastructure-as-Code (IaC) using Terraform

---

## 🛠️ Technologies Used

- AWS EC2
- AWS ECS (Fargate)
- AWS ALB & Target Groups
- AWS ACM
- AWS ECR
- Terraform
- Docker

---

## 🧪 Solved All Stages and their Endpoints

1. Public cloud & index page (contains the secret word): https://sachincareer.in.net 
2. Docker check: https://sachincareer.in.net/docker
3. Secret Word check: https://sachincareer.in.net/secret_word
4. Load Balancer check: https://sachincareer.in.net/loadbalanced
5. TLS check: https://sachincareer.in.net/tls

- `/` → Executes `bin/001`
- `/aws` → Executes `bin/002`
- `/docker` → Executes `bin/003`
- `/loadbalanced` → Executes `bin/004` with headers
- `/tls` → Executes `bin/005` with headers
- `/secret_word` → Executes `bin/006` with headers

---

## ⚙️ How to Run Locally

1. Build Docker image
 
docker build -t quest-app .
   
2. Run container

docker run -p 3000:3000 quest-app

3. Test locally

curl http://localhost:3000


☁️ Cloud Deployment (AWS)

1. Docker Image Push:

aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin <ECR-URL>
docker tag quest-app:latest <ECR-URL>/quest-app:latest
docker push <ECR-URL>/quest-app:latest

2. Terraform Apply

terraform init
terraform apply

3. ECS Deployment (if required)

- In AWS Console → ECS → Services → quest-service → Deployments → "Force new deployment".


🔐 Security Groups

- Ensure ports 80, 443, and 3000 are open in your ECS service’s security group.

📈 Health Check

Target group uses:

- Protocol: HTTP
- Path: /
- Port: 3000
- Healthy threshold: 2
- Interval: 30s

🧠 Given more time, I would improve...

- Add proper logging and error handling in the app
- Container health checks (HEALTHCHECK in Dockerfile)
- Set up CI/CD pipeline using GitHub Actions or AWS CodePipeline
- 

📁 Submission Checklist
- Hosted Git repo.
- All IaC (Terraform) files
- Dockerfile for Node.js app
- README with usage and architecture documentation
- Live deployment link
- Screenshots.







