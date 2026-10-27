# DevOps Capstone Project

[![CI Build](https://github.com/Bhavikesh/devops-capstone-project/actions/workflows/ci-build.yaml/badge.svg)](https://github.com/Bhavikesh/devops-capstone-project/actions/workflows/ci-build.yaml)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python 3.9](https://img.shields.io/badge/Python-3.9-green.svg)](https://shields.io/)

This repository contains the complete Customer Accounts REST API microservice built as the final Capstone Project for the **IBM DevOps and Software Engineering Professional Certificate**.

## Overview

The Customer Accounts microservice handles the complete lifecycle of customer accounts for an e-commerce platform following Agile principles, Test-Driven Development (TDD), application security best practices, Docker containerization, Kubernetes orchestration, and continuous integration/continuous delivery (CI/CD) automation.

## Project Architecture

The microservice follows the **Model-View-Controller (MVC)** architectural pattern:

```text
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   └── user-story.md       <- GitHub issue template for Agile user stories
│   └── workflows/
│       └── ci-build.yaml       <- GitHub Actions continuous integration workflow
├── deploy/
│   ├── deployment.yaml         <- Kubernetes Deployment manifest
│   └── service.yaml            <- Kubernetes Service manifest
├── service/                    <- Microservice core application package
│   ├── common/
│   │   ├── cli_commands.py     <- CLI commands for Flask
│   │   ├── error_handlers.py   <- REST API HTTP error handlers
│   │   ├── log_handlers.py     <- Production log configuration
│   │   └── status.py           <- Standard HTTP status codes
│   ├── config.py               <- Flask configuration object
│   ├── models.py               <- Persistent data model using Flask-SQLAlchemy
│   └── routes.py               <- REST API routes / endpoints
├── tekton/
│   ├── pipeline.yaml           <- Tekton CD pipeline
│   ├── pvc.yaml                <- PersistentVolumeClaim for Tekton workspace
│   └── tasks.yaml              <- Custom Tekton tasks
├── tests/                      <- Comprehensive test suite (98% coverage)
│   ├── factories.py            <- Factory Boy model generator
│   ├── test_cli_commands.py    <- Tests for CLI commands
│   ├── test_models.py          <- Unit tests for Account model
│   └── test_routes.py          <- REST API route & security unit tests
├── Dockerfile                  <- Production Docker container specification
├── Makefile                    <- Automation tasks and build targets
├── Procfile                    <- Process file for Gunicorn deployment
├── requirements.txt            <- Python dependencies
├── setup.cfg                   <- Linting & test configuration
└── user-story.md               <- Agile user story template
```

## REST API Endpoints

| Method | Endpoint | Description | Status Code |
|---|---|---|---|
| `GET` | `/` | Root URL; returns service metadata & account list URL | `200 OK` |
| `GET` | `/health` | Health check endpoint | `200 OK` |
| `POST` | `/accounts` | Create a new customer account | `201 Created` |
| `GET` | `/accounts` | List all customer accounts | `200 OK` |
| `GET` | `/accounts/<id>` | Read a specific customer account | `200 OK` / `404 Not Found` |
| `PUT` | `/accounts/<id>` | Update an existing customer account | `200 OK` / `404 Not Found` |
| `DELETE` | `/accounts/<id>` | Delete a customer account | `204 No Content` |

## Data Model

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | Integer | Primary Key | Unique account identifier |
| `name` | String(64) | Yes | Account holder's full name |
| `email` | String(64) | Yes | Account email address |
| `address` | String(256) | Yes | Physical street address |
| `phone_number` | String(32) | No | Optional phone contact |
| `date_joined` | Date | Yes | Account creation date (default: today) |

## Security Features

- **Flask-Talisman**: Configured with strict Content Security Policy (`CSP`), `X-Frame-Options: SAMEORIGIN`, `X-Content-Type-Options: nosniff`, and `Referrer-Policy: strict-origin-when-cross-origin`.
- **Flask-CORS**: Configured cross-origin resource sharing allowing clients to access REST endpoints (`Access-Control-Allow-Origin: *`).

## Running Tests & Code Quality

```bash
# Run unit tests and generate coverage report (98% achieved)
nosetests

# Run Flake8 linter
flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics
flake8 . --count --max-complexity=10 --max-line-length=127 --statistics

# Run Pylint (rated 10.00/10)
pylint service --rcfile=setup.cfg
```

## Docker Containerization

```bash
# Build the Docker image
docker build -t accounts:1.0 .

# Run the containerized service
docker run -d -p 8080:8080 -e DATABASE_URI="sqlite:////tmp/accounts.db" accounts:1.0
```

## License

Licensed under the Apache License, Version 2.0.
