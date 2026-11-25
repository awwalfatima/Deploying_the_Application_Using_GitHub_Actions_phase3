# Phase 3: Deploying the Application Using GitHub Actions

## 1. Project Overview

This phase focuses on implementing a Continuous Integration and Continuous Deployment (CI/CD) pipeline for the Zeetafin ERP application using GitHub Actions and AWS services.

The pipeline automates building Docker images, pushing them to Amazon Elastic Container Registry (ECR), and deploying the application to an Amazon EC2 instance.

## 2. Technologies and AWS Services Used

- GitHub – Source code management.
- GitHub Actions – CI/CD automation.
- Docker – Application containerization.
- Amazon ECR – Docker image storage.
- Amazon EC2 – Application hosting.
- AWS Systems Manager (SSM) – Remote deployment command execution.
- AWS IAM – Access control and permissions.
- Nginx – Reverse proxy and traffic routing.

## 3. CI/CD Workflow

The deployment process follows these steps:

1. Code is pushed to the main branch of the GitHub repository.
2. GitHub Actions automatically triggers the workflow.
3. AWS credentials are configured using GitHub repository secrets.
4. GitHub Actions authenticates with Amazon ECR.
5. Docker images for the backend and frontend are built.
6. The images are pushed to Amazon ECR.
7. AWS Systems Manager sends deployment commands to the EC2 instance.
8. The EC2 instance pulls the images from ECR.
9. Docker containers are created or updated.
10. Nginx routes incoming application requests to the frontend and backend services.

## 4. Application Containers

The deployment runs the following containers:

| Container | Purpose |
|---|---|
| zeetafin-backend | Backend application |
| zeetafin-frontend | Frontend application |
| zeetafin-db | PostgreSQL database |
| nginx | Reverse proxy and traffic routing |

## 5. Security Configuration

- AWS credentials are stored as GitHub repository secrets.
- IAM permissions control access to AWS resources.
- The EC2 instance uses an IAM role to access Amazon ECR and Systems Manager.
- AWS Systems Manager is used for remote deployment.

## 6. Application Access

The deployed application is accessible at:

http://54.194.185.138

## 7. Evidence and Screenshots

Screenshots demonstrating the Phase 3 implementation are available in:

evidence/

The evidence includes:

1. Successful GitHub Actions workflow execution.
2. Backend and frontend Docker images in Amazon ECR.
3. Zeetafin ERP application running in a web browser.
4. Docker containers running on the EC2 instance.

## 8. Outcome

The Phase 3 implementation successfully established an automated CI/CD pipeline using GitHub Actions and AWS services.

The pipeline builds and publishes Docker images to Amazon ECR and deploys the application to an EC2 instance through AWS Systems Manager.

This reduces manual deployment steps and provides a repeatable application deployment process.