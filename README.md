# smolla-tenancy

Tenant and organisation management service responsible for mapping authenticated identities to Smolla organisations, app roles, and SAML claim translation.

## Repository layout

```
backend/
    src/Smolla.Tenancy.Host/   ASP.NET Core web host (BFF / API)
    tests/Smolla.Tenancy.Tests/ xUnit unit + integration tests
frontend/                    Vue 3 + TypeScript app, served from /
```

## Local development

```
# Backend
cd backend
dotnet restore && dotnet build && dotnet test
dotnet run --project src/Smolla.Tenancy.Host

# Frontend (separate terminal)
cd frontend
npm install
npm run dev
```

## Workflows

- `ci.yml` — runs on every push and PR
- `deploy-prod.yml` — runs on push to `main`
- `deploy-staging.yml` — runs on push to `develop`
- `deploy-test.yml` — manual dispatch for shared test slot
- `release-please.yml` — opens release PRs based on conventional commits
- `sync-main-to-develop.yml` — back-merges hotfixes from `main` into `develop`

## Versioning

Managed by `release-please`; the canonical version lives in `version.txt` and is propagated to project files on each release.

## Licence

GNU Affero General Public License v3.0 — see [LICENSE](LICENSE).

Copyright (c) 2026 Adam Salisbury.

