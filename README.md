# Portfolio Platform

Microservices architecture demonstrating Go, Vue, AWS, and DevOps practices.

## Demo

🔑 [admin.gunarsk.com](https://admin.gunarsk.com) — `demo` / `demo123` (read-only)

## Services

| Service | Stack | Purpose |
|---------|-------|---------|
| [auth-service](https://github.com/GunarsK-portfolio/auth-service) | Go/Gin | JWT + Redis sessions |
| [admin-api](https://github.com/GunarsK-portfolio/admin-api) | Go/Gin | Admin CRUD |
| [public-api](https://github.com/GunarsK-portfolio/public-api) | Go/Gin | Public read-only API |
| [files-api](https://github.com/GunarsK-portfolio/files-api) | Go/Gin | S3 file management |
| [messaging-api](https://github.com/GunarsK-portfolio/messaging-api) | Go/Gin | Contact form API |
| [messaging-service](https://github.com/GunarsK-portfolio/messaging-service) | Go | RabbitMQ email worker |
| [admin-web](https://github.com/GunarsK-portfolio/admin-web) | Vue 3 | Admin dashboard |
| [public-web](https://github.com/GunarsK-portfolio/public-web) | Vue 3 | Portfolio site |
| [database](https://github.com/GunarsK-portfolio/database) | PostgreSQL | Migrations, RBAC |
| [infrastructure](https://github.com/GunarsK-portfolio/infrastructure) | Terraform | AWS + Docker Compose |
| [e2e-tests](https://github.com/GunarsK-portfolio/e2e-tests) | Playwright | End-to-end tests |

## Highlights

- 583+ unit tests, 197+ E2E steps
- RBAC with granular scopes per resource
- AWS: App Runner, Aurora, CloudFront, WAF
- CI/CD: GitHub Actions with security scanning

🌐 [gunarsk.com](https://gunarsk.com)
