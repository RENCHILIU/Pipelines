

# GitHub Actions for Spring Boot with Docker Hub Integration

## Overview
This repository contains a GitHub Actions workflow template that automates the process of building a Spring Boot project and pushing the resulting Docker image to Docker Hub. This setup is ideal for continuous integration and deployment (CI/CD) pipelines, ensuring that every change to your codebase is automatically tested, built, and made available as a Docker image.

## Features
- **Automated Build**: Automatically builds your Spring Boot application using Maven.
- **Docker Integration**: Creates a Docker image and pushes it to your Docker Hub repository.
- **Multi-Architecture Support**: Builds images for both AMD64 and ARM64 architectures, ensuring compatibility across different platforms.
- **Manual Trigger Option**: Allows manual triggering of the workflow via GitHub's UI, in addition to automatic triggering on code push.

## Prerequisites
Before using this workflow, ensure you have the following:
- A GitHub account and a repository with a Spring Boot project.
- A Docker Hub account and a repository where images will be pushed.
- Docker and Maven properly set up in your project.

## Setup and Configuration
1. **GitHub Secrets**: 
   - Set up `DOCKER_HUB_USERNAME` and `DOCKERHUB_TOKEN` in your repository's secrets to securely store your Docker Hub credentials.

2. **Workflow File**:
   - The workflow is defined in `.github/workflows/docker_image.yml`. （https://github.com/RENCHILIU/SpringbootPipeline/blob/main/.github/workflows/docker_image.yml）
   - Customize the workflow as per your project's needs, especially the `context`, `file`, and `tags` fields under the `Build and Push` job.

3. **Dockerfile**:
   - Ensure your project contains a Dockerfile at its root. This Dockerfile should be configured to build your Spring Boot application.

## Usage
- **Automatic Trigger**: The workflow runs automatically upon pushing code to the configured branch (default is `main`).
- **Manual Trigger**: You can also trigger the workflow manually from the GitHub Actions tab in your repository.


ref:
https://github.com/actions/checkout
https://github.com/docker/setup-buildx-action
https://github.com/docker/login-action
https://github.com/docker/build-push-action
