# Base Project: Docker Image for Python Applications

![Badge](https://img.shields.io/badge/DevSecOps-Active-brightgreen)
![Badge](https://img.shields.io/badge/Python-3.9-blue)
![Badge](https://img.shields.io/badge/Docker-Supported-blue)
![Badge](https://img.shields.io/badge/Secure-With%20Trivy%20&%20Bandit-brightgreen)

This project provides a **base Docker image** for Python applications, optimized for **security** and **efficiency**. The image includes essential dependencies and security tools to ensure that applications built on top of it are secure and reliable.

## Table of Contents

- [Description](#description)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Security](#security)
- [Contributing](#contributing)
- [License](#license)

## Description

This project offers a **base Docker image** for Python applications, designed with a focus on **security** and **DevSecOps best practices**. The image includes:

- **Python 3.9**: A stable and widely-used version.
- **Essential Dependencies**: Pre-installed to speed up development.
- **Security Tools**: Integration with Trivy and Bandit for vulnerability scanning.

The base image is used in other projects to build Python applications securely and efficiently.

## Features

- **Continuous Integration (CI)**: Uses GitHub Actions to automate testing and builds.
- **Integrated Security**:
  - Vulnerability scanning with **Trivy**.
  - Static code analysis with **Bandit**.
  - Dependency verification with **Safety**.
- **Image Optimization**: Uses `python:3.9-slim` to reduce image size.
- **Automatic Updates**: Dependencies are automatically updated in each build.

## Installation

To use this base image in your project, follow these steps:

1. **Clone the repository**:

   ```bash
   git clone https://github.com/yourusername/base-project.git
   cd base-project

2. **Build Image**:
      
      ```bash
      docker build -t yourusername/base-image:latest -f Dockerfile.base .

3. **Push the image to Docker Hub (optional)**:

      ```bash
      docker push yourusername/base-image:latest

## Usage

To use this base image in your project, simply reference the image in your Dockerfile:

   ```bash
      dockerfile
      Copy
      FROM yourusername/base-image:latest

      WORKDIR /app

      # Copy the application code
      COPY . .

      # Install additional dependencies (if needed)
      RUN pip install -r requirements.txt

      # Command to run the application
      CMD ["python", "app.py"]

```

## Security
This project follows DevSecOps best practices to ensure the security of applications built on this base image.

## Security Tools

Trivy: Scans the Docker image for vulnerabilities.

Bandit: Performs static analysis of Python code to detect common vulnerabilities.

Semgrep: Scans code and configurations for insecure patterns.

Checkov: Scans the Dockerfile for insecure configurations.

Safety: Checks Python dependencies for known vulnerabilities.

Fixed Vulnerabilities
During the development of this project, several vulnerabilities were identified and fixed, including:

* CVE-2023-5752: A vulnerability in pip that allowed Mercurial configuration injection.

* CVE-2022-40897: A Denial of Service (ReDoS) vulnerability in setuptools.

* CVE-2024-6345: A Remote Code Execution (RCE) vulnerability in setuptools.

These vulnerabilities were fixed by updating the dependencies to their latest versions.

Security Practices

* Automatic Updates: Dependencies are automatically updated in each build.

* Continuous Scanning: Integration of Trivy, Bandit, Semgrep, and Checkov in the CI/CD pipeline.

* Secrets Management: Use of GitHub Secrets to securely store credentials.

## CI/CD Pipeline
The CI/CD pipeline is configured to ensure that the base image is secure and production-ready. Below is a breakdown of the pipeline stages:

Pipeline Stages

1. Checkout Code:

      * Clones the repository to start the process.

2. Security Scanning (SAST):

      * Semgrep: Scans the code for insecure patterns.

      * Checkov: Scans the Dockerfile for insecure configurations.

3. Build Docker Image:

      * Builds the Docker image using the Dockerfile.

4. Image Scanning (SAST):

      * Trivy: Scans the Docker image for vulnerabilities.

5. Push to Docker Hub:

      * If the pipeline runs on the main branch, the image is pushed to Docker Hub.

## How to Interpret Results

Semgrep: If issues are found, the pipeline will fail, and a detailed report will be available in the logs.

Checkov: If insecure configurations are detected, the pipeline will fail, and a report will be generated.

Trivy: If vulnerabilities are found, the pipeline will fail, and a detailed report will be available.

## License
This project is licensed under the MIT License. See LICENSE for more details.

![Build Status](https://github.com/yourusername/base-project/actions/workflows/ci-cd.yml/badge.svg)
![Trivy Scan](https://img.shields.io/badge/Trivy-Scan%20Passed-brightgreen)
![Bandit Scan](https://img.shields.io/badge/Bandit-Scan%20Passed-brightgreen)
![License](https://img.shields.io/badge/License-MIT-blue)