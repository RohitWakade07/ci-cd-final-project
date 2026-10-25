# CI/CD Tools and Practices Final Project Template

## ci-cd-final-project

This repository contains a Node.js/Express.js version of the counter service for the Final Project of the Coursera course **CI/CD Tools and Practices**.

## Features

- RESTful API for managing counters
- In-memory storage
- Comprehensive error handling
- Security middleware (Helmet, CORS)
- Logging middleware
- Full test coverage with Jest
- Docker support
- Health check endpoint

## API Endpoints

- `GET /` - Service information
- `GET /health` - Health check
- `GET /counters` - List all counters
- `POST /counters/:name` - Create a new counter
- `GET /counters/:name` - Read a specific counter
- `PUT /counters/:name` - Increment a counter
- `DELETE /counters/:name` - Delete a counter

## Setup

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Run the application:**
   ```bash
   npm start
   ```

3. **Run tests:**
   ```bash
   npm test
   ```

4. **Run linting:**
   ```bash
   npm run lint
   ```

## CI/CD Pipeline

This project uses:
- **GitHub Actions** for Continuous Integration (CI)
- **OpenShift Pipelines (Tekton)** for Continuous Deployment (CD)

### GitHub Actions Workflow
The CI workflow (`.github/workflows/workflow.yml`) runs on every push and pull request to `main`:
- Checkout code
- Setup Node.js 20
- Install dependencies (`npm ci`)
- Lint with ESLint (`npm run lint`)
- Run unit tests with Jest (`npm test`)

### Tekton Tasks
The CD pipeline (`.tekton/tasks.yml`) includes:
- **cleanup** – Cleans the workspace before each run
- **eslint** – Runs ESLint linting on the source code
- **jest-test** – Runs Jest unit tests

## License

This project is licensed under the Apache License 2.0.