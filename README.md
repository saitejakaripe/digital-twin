# AI Digital Twin

Full-stack AI digital twin built with a Python backend, a Next.js interface, and AWS deployment infrastructure. The project turns profile/context data into an interactive digital representative that can be deployed as a cloud-native service.

## What This Project Shows

- Python backend for loading profile facts, style guidance, LinkedIn context, and supporting resources.
- API/serverless entry points for running the twin locally or as an AWS Lambda-style handler.
- Next.js frontend for presenting and interacting with the digital twin experience.
- Terraform-managed AWS infrastructure for repeatable deployment.
- Deployment and teardown scripts that make the project easier to operate.

## Architecture

```text
digital-twin/
|-- backend/
|   |-- server.py             # Local API entry point
|   |-- lambda_handler.py     # Serverless handler
|   |-- context.py            # Context assembly for the twin
|   |-- resources.py          # Data/resource loading helpers
|   `-- data/                 # Profile facts, style notes, summary, source PDF
|-- frontend/
|   |-- app/
|   |-- components/twin.tsx
|   `-- package.json
|-- terraform/                # AWS infrastructure definition
|-- scripts/
|   |-- deploy.sh
|   `-- destroy.sh
`-- .env.example
```

## Tech Stack

- Python, FastAPI-style service structure, serverless handler patterns
- Next.js, TypeScript, React
- AWS, Terraform, shell deployment scripts
- Structured profile/context data for AI-persona behavior

## Run Locally

Backend:

```bash
cd backend
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python server.py
```

Frontend:

```bash
cd frontend
npm install
npm run dev
```

## Deploy

Copy `.env.example`, add the required environment values, then use the deployment scripts:

```bash
./scripts/deploy.sh
```

To destroy the provisioned cloud resources:

```bash
./scripts/destroy.sh
```

## Recruiter Notes

This repo highlights end-to-end AI product work: backend context engineering, frontend delivery, cloud infrastructure, and deployment automation. Terraform remains part of the project, but the application logic lives primarily in Python and TypeScript.
