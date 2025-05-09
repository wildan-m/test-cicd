# CI/CD Project

## Overview
This project demonstrates a CI/CD pipeline using GitHub Actions to automate the build and deployment of a Dockerized application. The application is built using a Dockerfile and managed with Docker Compose.

## Project Structure
```
ci-cd-project
├── .github
│   └── workflows
│       └── staging.yml       # GitHub Actions workflow for CI/CD
├── docker-compose.yml         # Defines services for the application
├── Dockerfile.dev             # Dockerfile for building the development image
├── src
│   └── app.js                 # Main application file
└── README.md                  # Project documentation
```

## Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd ci-cd-project
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

## Usage
- Push changes to the `staging` branch to trigger the CI/CD pipeline defined in `.github/workflows/staging.yml`.
- The pipeline will check out the repository, build the application, and run the container.

## Assumptions
- Docker and Docker Compose are installed on your machine.
- The application is designed to run on port 3000.
- The repository is hosted on GitHub.

## License
This project is licensed under the MIT License.