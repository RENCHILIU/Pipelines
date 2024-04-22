# Useful Pipelines Built with GitHub Actions

## Usage

1. Clone this project and copy it to your personal project.
2. Based on your needs, delete unused pipelines and retain the necessary ones.
3. Customize the `.github/workflows` and `Dockerfile`.

## Introduction

This repository contains a GitHub Actions workflow template that automates the process of building different projects (refer to the folders) and pushing the resulting Docker images to Docker Hub. This setup is ideal for continuous integration and deployment (CI/CD) pipelines, ensuring that every change to your codebase is automatically tested, built, and made available as a Docker image.

## Prerequisites

Before using this workflow, ensure you have the following:
- A GitHub account and a repository with a Spring Boot project.
- A Docker Hub account and a repository where images will be pushed.
- Project-specific setup and knowledge.

## Setup and Configuration

1. **GitHub Secrets**:
   - Set up `DOCKER_HUB_USERNAME` and `DOCKER_HUB_TOKEN` in your repository's secrets to securely store your Docker Hub credentials.
     ![Docker Hub Credentials](https://github.com/RENCHILIU/SpringbootPipeline/assets/21353882/a6ec43ce-f646-42d3-9534-2d0869556329)

2. **Workflow File**:
   - The workflow is defined in `.github/workflows`. [View Workflow](https://github.com/RENCHILIU/SpringbootPipeline/blob/main/.github/workflows/)
   - Customize the workflow according to your project's needs, especially the `context`, `file`, and `tags` fields under the `Build and Push` job.

3. **Dockerfile**:
   - By default, the workflow file allows user inputs to change the `working_path`, `docker_image_name`, and `platform`. Customize it to suit your needs.
     ![Dockerfile Customization](https://github.com/RENCHILIU/Pipelines/assets/21353882/3c53c9b8-610f-476d-9c64-067c69040a82)

## Trigger

- **Manual Trigger**: By default, trigger the workflow manually from the GitHub Actions tab in your repository.
- **Automatic Trigger**: Uncomment the below code in `.github/workflows` to make the workflow run automatically upon pushing code to the configured branch (default is `main`).

```yaml
# push:
#   branches: [main]
