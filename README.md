## React Application CI/CD Pipeline

This repository contains a CI/CD pipeline for building a Docker image of a React application, tagging it with "latest" and the GitHub run number, and pushing it to both AWS Elastic Container Registry (ECR) and Docker Hub automatically with every push to the main branch.
---

## Introduction

In modern software development, a robust and automated CI/CD pipeline is essential to streamline the process of building, testing, and deploying applications. This project sets up an efficient pipeline for a React application, providing numerous benefits for your development workflow.

## Benefits

### 1. **Dual Image Distribution**
   By pushing the Docker image to both AWS ECR and Docker Hub simultaneously, you gain redundancy and flexibility. Here's why it's advantageous:

   - **High Availability**: If one container registry experiences downtime or issues, your application remains accessible through the other.
   
   - **Geo-Distribution**: AWS ECR and Docker Hub have different global distributions. Pushing to both ensures that your application is available to users worldwide with lower latency.
   
   - **Vendor Independence**: Diversifying the storage locations mitigates the risk of vendor-specific limitations or changes affecting your deployments.

### 2. **Tagging with "latest" and GitHub Run Number**
   Tagging Docker images with "latest" and the GitHub run number offers several advantages:

   - **Versioning**: The "latest" tag simplifies the process of deploying the most recent version of your application.
   
   - **Traceability**: Each image is tagged with the GitHub run number, making it easy to trace back to the specific commit and build that produced the image. This is invaluable for debugging and auditing purposes.
   
   - **Rollback**: In case of issues with a new release, you can easily revert to a previous image tagged with a specific run number.

---

## Getting Started

To use this CI/CD pipeline in your project, follow these steps:

1. **Clone this repository** to your local machine.

2. **Configure Secrets**:
   - Add your AWS ECR and Docker Hub credentials as secrets in your GitHub repository.
   
3. **Adjust Configuration**:
   - Modify the pipeline configuration files (e.g., `.github/workflows/ci-cd.yml`) to suit your specific needs, such as changing the application name and repository URLs.

4. **Push to Main Branch**:
   - Pushing code to the main branch will trigger the CI/CD pipeline automatically.

---

## Usage

1. **Commit and Push**:
   - Make changes to your React application code.
   - Commit and push your changes to the main branch.

2. **GitHub Actions**: 
   - GitHub Actions will automatically trigger the CI/CD pipeline.
   
3. **Image Availability**:
   - After a successful pipeline run, your Docker image will be available on both AWS ECR and Docker Hub with appropriate tags.

4. **Deployment**:
   - Deploy your application using the Docker image, either by manually selecting the desired tag or by using the "latest" tag for the most recent version.
