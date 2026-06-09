# mcp-Repo

Minimal Node.js web app that returns a welcome message and includes a GitHub Actions CI/CD pipeline to deploy to Azure App Service.

Getting started

1. Install dependencies

```bash
npm ci
```

2. Run locally

```bash
npm start
```

3. Run tests

```bash
npm test
```

Deployment

This repository includes a Bicep template at `infra/main.bicep` and a GitHub Actions workflow at `.github/workflows/ci-cd.yml` that:
- runs CI (install, lint, test)
- deploys infra using the Bicep template
- deploys the app to Azure App Service
- runs a post-deploy smoke test

Required GitHub Secrets:
- `AZURE_CREDENTIALS` — service principal JSON for `azure/login`
- `AZURE_RESOURCE_GROUP` — target resource group
- `AZURE_WEBAPP_NAME` — web app name
- `AZURE_WEBAPP_URL` — app URL used for smoke test
