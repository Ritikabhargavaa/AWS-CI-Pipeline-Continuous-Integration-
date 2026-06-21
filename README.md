# AWS CI Pipeline (Continuous Integration)

## Overview

This project demonstrates how to implement an automated Continuous Integration (CI) pipeline using AWS managed services. The pipeline automatically triggers whenever code is pushed to the GitHub repository, builds a Docker image, and pushes it to Docker Hub.

## Tech Stack

* **Cloud Provider:** AWS (Amazon Web Services)
* **Services:** AWS CodePipeline, AWS CodeBuild, AWS Systems Manager Parameter Store, IAM Roles
* **Version Control:** GitHub
* **Containerization:** Docker
* **Application:** Python (Flask)

## Architecture Workflow

1. Developer pushes code to the GitHub repository.
2. AWS CodePipeline detects the code change and triggers the pipeline.
3. AWS CodeBuild executes the `buildspec.yml` file.
4. Dependencies are installed and the application is built.
5. Docker image is created.
6. Docker image is pushed to Docker Hub.

### Workflow Diagram

```text
GitHub
   |
   v
AWS CodePipeline
   |
   v
AWS CodeBuild
   |
   v
Build Docker Image
   |
   v
Push to Docker Hub
```

## Key Features

* Automated CI pipeline using AWS services.
* Secure storage of Docker Hub credentials using AWS Systems Manager Parameter Store.
* Docker image build and deployment automation.
* Scalable and reliable AWS-native architecture.

## Prerequisites

* AWS Account
* GitHub Repository
* Docker Hub Account
* IAM Permissions for CodePipeline and CodeBuild

## Setup Steps

### Step 1: Create Parameter Store Entries

Create Secure String parameters for:

* Docker Username
* Docker Password
* Docker Registry URL

### Step 2: Create CodeBuild Project

* Connect GitHub repository.
* Enable **Privileged Mode** for Docker builds.
* Configure service role permissions.

### Step 3: Add buildspec.yml

Place the `buildspec.yml` file in the root directory of the repository.

### Step 4: Create CodePipeline

* Source Provider: GitHub
* Build Provider: AWS CodeBuild
* Connect the CodeBuild project.

### Step 5: Push Code

Push code changes to GitHub and verify that the pipeline is triggered automatically.

## Security

* Credentials are stored securely in AWS Systems Manager Parameter Store.
* IAM roles are used to grant least-privilege permissions.
* No sensitive information is hardcoded in the source code.

## Future Enhancements

* Add Continuous Deployment (CD) using AWS ECS or EKS.
* Implement automated testing stages.
* Add security and vulnerability scanning for Docker images.

## Reference

Built as part of the AWS Zero to Hero learning journey inspired by Abhishek Veeramalla.

