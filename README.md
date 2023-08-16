# Node.js App CI/CD Pipeline with GitHub Actions

This repository contains a simple Node.js application along with a GitHub Actions workflow that implements a Continuous Integration/Continuous Deployment (CI/CD) pipeline. The pipeline is designed to automatically build, test, and deploy the Node.js application to Docker Hub whenever changes are pushed to the `main` branch.

## Application Overview

The Node.js application in this repository is a basic example to demonstrate the CI/CD pipeline setup. You can replace it with your own Node.js application code. The application consists of the following components:

- `app.js`: The main application file.
- `package.json`: Node.js package configuration.
- `Dockerfile`: Dockerfile for building a Docker image of the application.

## Workflow Details

The CI/CD pipeline is defined using GitHub Actions. The workflow is triggered on every push to the `main` branch. The pipeline consists of the following stages:

1. **Checkout**: Checks out the latest code from the repository.
2. **Build**: Builds the Node.js application.
4. **Build Docker Image**: Builds a Docker image of the application using the provided `Dockerfile`.
5. **Push to Docker Hub**: Pushes the Docker image to your specified Docker Hub repository.

## Getting Started

To set up the CI/CD pipeline for your Node.js application, follow these steps:

1. **Clone the Repository**: Clone this repository to your local machine.
   
    ```sh
    git clone https://github.com/gurpreet-legend/github-actions-nodejs.git
    cd github-actions-nodejs
    ```

2. **Replace Application Code**: Replace the existing Node.js application code with your own code.

3. **Docker Hub Credentials**:

    - Open the GitHub repository.
    - Go to "Settings" > "Secrets".
    - Create two secrets: `DOCKER_USERNAME` and `DOCKER_PASSWORD`, containing your Docker Hub username and password (access token) respectively. These secrets will be used to push the Docker image to Docker Hub.

4. **Configure Docker Image Name**:
   
    - Open the `.github/workflows/node.js.yml` file.
    - In the `jobs.build.steps` section, replace `gurpreet2701/github-actions-nodejs` with the desired name for your Docker image.

5. **Commit and Push**: Commit your changes and push them to the `main` branch.
   
    ```sh
    git add .
    git commit -m "Updated application code and Docker image name"
    git push origin main
    ```

6. **GitHub Actions**: Navigate to the "Actions" tab in your GitHub repository. You should see the CI/CD workflow running.

## Workflow Customization

- You can modify the workflow in the `.github/workflows/node.js.yml` file to adapt it to your specific needs. For example, you can add additional stages, tests, or deployment steps.

- Remember to customize the Docker image name and any other relevant settings in the workflow file.

---
