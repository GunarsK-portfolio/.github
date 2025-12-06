# Portfolio Platform

Full-stack microservices architecture showcasing **Go, Vue.js, AWS, and modern DevOps practices**. Designed to demonstrate production-ready patterns, secure architecture, and comprehensive testing.

---

## Demo

🌐 [Portfolio Website](https://gunarsk.com)  
🔑 [Portfolio Admin Website](https://admin.gunarsk.com) — read-only demo (`demo` / `demo123`)

---

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

---

## Highlights

- ✅ 583+ unit tests, 197+ end-to-end test steps  
- 🔒 RBAC with granular scopes per resource  
- ☁️ AWS: App Runner, Aurora, CloudFront, WAF  
- 🚀 CI/CD: GitHub Actions with multi-layer security scanning and OIDC deployments  

---

## Architecture Overview

```mermaid
flowchart TD

    subgraph Frontend["Vue 3 Frontend"]
        PW["Public Site 🖥️ Vue"]
        AW["Admin Panel 🖥️ Vue"]
    end

    subgraph Backend["Go Microservices"]
        AUTH["Auth Service 🟢 Go"]
        API["Public API 🟢 Go"]
        ADM["Admin API 🟢 Go"]
        FILES["Files API 🟢 Go"]
        MSG["Messaging API 🟢 Go"]
        WORKER["Messaging Worker 🟢 Go"]
    end

    subgraph Data["AWS Data Layer"]
        CACHE["Redis 🟦"]
        DB["PostgreSQL 🐘"]
        S3["S3 ☁️"]
        MQ["RabbitMQ 🐰"]
        SES["SES ✉️"]
    end

    %% Connections
    PW --> API
    PW --> MSG
    PW --> FILES
    AW --> AUTH
    AW --> FILES
    AW --> ADM
    AW --> MSG
    API --> DB
    ADM --> DB
    AUTH --> DB
    MSG --> DB
    MSG --> MQ
    WORKER --> MQ
    WORKER --> DB
    WORKER --> SES
    AUTH --> CACHE
    FILES --> S3
