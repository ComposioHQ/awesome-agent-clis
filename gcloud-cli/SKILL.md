---
name: "Google Cloud CLI (gcloud)"
description: "Manage GCP resources — Compute, Cloud Run, GKE, BigQuery, IAM, and more. Use when an agent needs to provision GCP infrastructure, deploy to Cloud Run, query BigQuery, or manage GCP projects."
---

# Google Cloud CLI (gcloud)

Manage GCP resources from the terminal.

- **Docs**: https://cloud.google.com/sdk/gcloud

## Installation

```bash
brew install google-cloud-sdk
gcloud init
gcloud auth login
```

## Key Commands

```bash
gcloud compute instances list --format=json
gcloud run deploy SERVICE --image IMAGE --region REGION
gcloud functions deploy FUNCTION --runtime python311 --trigger-http
gcloud projects list --format=json
gcloud iam service-accounts list --format=json
gcloud config set project PROJECT_ID
```

## Agent-Friendly Features

- `--format=json` for structured output
- Service account auth for non-interactive use
- `--quiet` flag to suppress prompts
- `--project` to target specific projects
