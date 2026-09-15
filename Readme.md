# P0 – GitHub Actions AWS Test

Simple test repository to learn and validate a basic **GitHub Actions CI/CD pipeline with AWS**.

## Objective

* Trigger GitHub Actions on code push.
* Install dependencies.
* Run basic application tests.
* Build the application.
* Deploy to an AWS EC2 instance.
* Validate the deployment.

## Tech Stack

* GitHub
* GitHub Actions
* AWS EC2
* Python 3.12
* FastAPI
* Uvicorn

## Pipeline Flow

```text
Developer
    ↓
Git Push
    ↓
GitHub Repository
    ↓
GitHub Actions
    ↓
Checkout Code
    ↓
Setup Python
    ↓
Install Dependencies
    ↓
Run Tests
    ↓
Build / Validate
    ↓
Deploy to AWS EC2
    ↓
Application Running
```

## Repository Structure

```text
.
├── app/
│   └── main.py
├── tests/
│   └── test_main.py
├── requirements.txt
├── .gitignore
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml
```

## GitHub Secrets

The following secrets are required for deployment:

```text
AWS_HOST
AWS_USERNAME
AWS_SSH_KEY
```

Do not store AWS credentials, SSH private keys, or other secrets directly in the repository.

## Run Locally

```bash
python3.12 -m venv venv
source venv/bin/activate

pip install -r requirements.txt

uvicorn app.main:app --host 0.0.0.0 --port 8000
```

Application:

```text
http://localhost:8000
```

## GitHub Actions

The workflow is located at:

```text
.github/workflows/deploy.yml
```

The workflow is triggered when code is pushed to the configured branch.

## P0 Scope

This is a **basic learning/test pipeline**.

It intentionally keeps the architecture simple and focuses on understanding:

* GitHub Actions workflow
* Secrets
* CI execution
* SSH-based EC2 deployment
* Basic AWS deployment
* Application validation
