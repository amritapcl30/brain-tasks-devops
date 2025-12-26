Brain Tasks App – AWS EKS Deployment
This repository demonstrates deploying a React application to a production-ready Kubernetes environment using Docker, Amazon EKS, and an AWS CI/CD pipeline.
________________________________________
📌 Project Overview
The Brain Tasks App is a React-based web application that is:
•	Containerized using Docker
•	Stored in Amazon ECR
•	Deployed on Amazon EKS (Kubernetes)
•	Automatically built and deployed using AWS CodePipeline and CodeBuild
________________________________________
🧰 Tech Stack
•	Frontend: React
•	Containerization: Docker
•	Registry: Amazon ECR
•	Orchestration: Amazon EKS
•	CI/CD: AWS CodePipeline, AWS CodeBuild
•	Monitoring: Amazon CloudWatch
•	Version Control: GitHub
________________________________________
🚀 Run Locally
git clone https://github.com/Vennilavan12/Brain-Tasks-App.git
cd Brain-Tasks-App
npm install
npm start
App runs on:
http://localhost:3000
________________________________________
🐳 Docker Build & Run
docker build -t brain-tasks-app .
docker run -p 3000:80 brain-tasks-app
________________________________________
☸️ Kubernetes Deployment (EKS)
Kubernetes manifests used:
•	deployment.yaml – Application deployment
•	service.yaml – LoadBalancer service
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
Get application endpoint:
kubectl get svc brain-tasks-service
________________________________________
🔄 CI/CD Pipeline Flow
GitHub
  ↓
AWS CodePipeline
  ↓
AWS CodeBuild
  ├─ Build Docker image
  ├─ Push image to Amazon ECR
  └─ Deploy to Amazon EKS using kubectl
________________________________________
⚙️ CodeBuild
The buildspec.yml file:
•	Authenticates to Amazon ECR
•	Builds and pushes Docker image
•	Updates kubeconfig for EKS
•	Deploys Kubernetes manifests using kubectl
________________________________________
❗ CodeDeploy Note
AWS CodeDeploy was evaluated but not used, as it does not support Amazon EKS as a compute platform.
Deployment to EKS is handled using AWS CodeBuild with kubectl, which aligns with AWS best practices for Kubernetes deployments.
________________________________________
📊 Monitoring
•	AWS CloudWatch logs for:
o	CodeBuild
o	CodePipeline
•	Kubernetes pod logs:
kubectl logs <pod-name>
________________________________________
📎 Submission Info
•	GitHub Repo: (this repository)
•	Application Endpoint: (LoadBalancer DNS / ARN)
•	Additional Documentation: Detailed deployment report included separately
________________________________________
✅ Summary
This project showcases a complete CI/CD workflow for deploying a containerized React application on Amazon EKS using AWS-native tools and production-ready practices.
