# Syrql Status Page

This repository contains the status page for the Syrql platform, powered by [Upptime](https://upptime.js.org).

## Live Status

Visit [status.syrql.com](https://status.syrql.com) to see the current status of all services.

## Monitored Services

### Production
- **Frontend** - https://syrql.com
- **API** - https://api.syrql.com/healthz
- **API GraphQL** - https://api.syrql.com/hello
- **Upload Service** - https://upload.syrql.com/health

### Staging
- **Frontend** - https://staging.syrql.com
- **API** - https://api-staging.syrql.com/healthz
- **Upload Service** - https://upload-staging.syrql.com/health

## Setup

### 1. Create GitHub Repository

Create a new repository named `status` under the `syrql` organization.

### 2. Configure Secrets

Add the following secrets to the repository:

| Secret | Description |
|--------|-------------|
| `GH_PAT` | GitHub Personal Access Token with `repo` and `workflow` scopes |

### 3. Configure DNS

Add a CNAME record:
```
status.syrql.com -> syrql.github.io
```

### 4. Enable GitHub Pages

1. Go to Settings > Pages
2. Select `gh-pages` branch as source
3. The site will be available at status.syrql.com after DNS propagation

## How It Works

- GitHub Actions run every 5 minutes to check all endpoints
- Results are stored as GitHub commits
- Response time graphs are generated daily
- Incidents are automatically created as GitHub Issues
- Email notifications are sent when services go down

## Configuration

Edit `.upptimerc.yml` to:
- Add/remove monitored sites
- Change notification settings
- Adjust response time thresholds
- Customize the status page appearance

## License

MIT
