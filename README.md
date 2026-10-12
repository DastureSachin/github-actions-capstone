# GitHub Actions Capstone

An end-to-end CI/CD project using Flask, Pytest, Docker, Docker Hub, and GitHub Actions.

## Workflow Status

![Main Pipeline](https://github.com/DastureSachin/github-actions-capstone/actions/workflows/main-pipeline.yml/badge.svg)

![PR Pipeline](https://github.com/DastureSachin/github-actions-capstone/actions/workflows/pr-pipeline.yml/badge.svg)

![Scheduled Health Check](https://github.com/DastureSachin/github-actions-capstone/actions/workflows/health-check.yml/badge.svg)

## Features

- Flask application with a health endpoint.
- Automated testing with Pytest.
- Reusable GitHub Actions workflows.
- Docker image publishing with `latest` and commit SHA tags.
- Pull request validation without Docker publishing.
- Main branch CI/CD with a production deployment simulation.
- Scheduled and manually triggered container health checks.

## Architecture

```mermaid
flowchart TD
    A[Pull Request] --> B[Build and Test]
    B --> C[PR Summary]
    D[Push to main] --> E[Build and Test]
    E --> F[Build and Push Docker Image]
    F --> G[Production Deployment Simulation]
    H[Scheduled or Manual Trigger] --> I[Container Health Check]
    I --> J[Health Report]
```

## Run Locally

Install dependencies:

```bash
python -m pip install -r requirements.txt
```

Run tests:

```bash
python -m pytest -v
```

Start the app:

```bash
python app.py
```

Open `http://localhost:5000/health` to check the health endpoint.

## Required Secrets

Configure `DOCKER_USERNAME` and `DOCKER_TOKEN` in the repository Actions secrets.


