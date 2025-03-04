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

      docker build -t yourusername/base-image:latest -f Dockerfile.base .

3. **Push the image to Docker Hub (optional)**:

      docker push yourusername/base-image:latest

## Usage

To use this base image in your project, simply reference the image in your Dockerfile:

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
Security
This project follows DevSecOps best practices to ensure the security of applications built on this base image.

## Security Tools
Trivy: Scans the Docker image for vulnerabilities.

Bandit: Performs static analysis of Python code to detect common vulnerabilities.

Safety: Checks Python dependencies for known vulnerabilities.

Fixed Vulnerabilities
During the development of this project, several vulnerabilities were identified and fixed, including:

CVE-2023-5752: A vulnerability in pip that allowed Mercurial configuration injection.

CVE-2022-40897: A Denial of Service (ReDoS) vulnerability in setuptools.

CVE-2024-6345: A Remote Code Execution (RCE) vulnerability in setuptools.

These vulnerabilities were fixed by updating the dependencies to their latest versions.

Security Practices
Automatic Updates: Dependencies are automatically updated in each build.

Continuous Scanning: Integration of Trivy and Bandit in the CI/CD pipeline.

Secrets Management: Use of GitHub Secrets to securely store credentials.


