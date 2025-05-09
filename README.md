# CI/CD Project

## Overview
This project demonstrates a CI/CD pipeline using GitHub Actions to automate the build and deployment of a Dockerized application. The application is built using a Dockerfile and managed with Docker Compose.

## Project Structure
```
.
├── .github/
│   └── workflows/        # GitHub Actions workflows
│       └── staging.yml   # Staging deployment workflow
├── docker-compose.yml    # Defines services for the application
├── Dockerfile.dev        # Dockerfile for building the development image
├── package.json          # Node.js package configuration
├── src/
│   └── app.js            # Main application file
└── README.md             # Project documentation
```

## Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd test-cicd
   ```

2. **Build the Docker Image**
   To build the Docker image for the development environment, run:
   ```bash
   docker build -f Dockerfile.dev -t my-app .
   ```

3. **Run the Application**
   Use Docker Compose to run the application:
   ```bash
   docker-compose up
   ```

4. **Access the Application**
   The application will be accessible at `http://localhost:3000`.

## CI/CD Pipeline

The project includes a GitHub Actions workflow that automatically builds and deploys the application:

1. **Trigger**
   - The pipeline is triggered when changes are pushed to the `staging` branch.

2. **Pipeline Steps**
   - Checks out the repository code
   - Sets up Docker Buildx
   - Builds the Docker image using the development Dockerfile
   - Runs the container to verify it starts correctly
   - Extracts build artifacts from the container

## Assumptions
- Docker and Docker Compose are installed on your machine.
- The application is designed to run on port 3000.
- The repository is hosted on GitHub.

## License
This project is licensed under the MIT License.