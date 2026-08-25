# FinanceCRM

Self-hosted financial CRM — transaction tracking, expense management, ROI analytics, and granular access control.

## Overview

FinanceCRM is a financial management tool for tracking income, expenses, and profitability across multiple wallets and team members. It features dynamic role-based permissions (50+ nodes), real-time collaboration via WebSocket, and multi-currency support. Built as a personal project to solve real bookkeeping pain points.

## Features

- Multi-wallet financial tracking (multiple currencies and payment processors)
- Income and expense management with flexible EAV categories
- Per-user and per-team ROI analytics
- Dynamic RBAC with 50+ permission nodes and per-user overrides
- Real-time updates via Socket.io
- Audit trail for all financial operations
- Internationalization (EN/RU/UA)
- Demo mode with fake seed data

## Demo

Live demo: [financecrm.opsctl.tech](https://financecrm.opsctl.tech)

Demo credentials on login page.

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 18, TypeScript, Tailwind CSS, Vite |
| Backend | Node.js, Express 5, Prisma 7, PostgreSQL, Redis, Socket.io |
| Auth | JWT + dynamic RBAC (roles, permissions, per-user overrides) |
| i18n | react-i18next (EN/RU/UA) |
| Process | PM2 (cluster mode) |
| CI/CD | GitHub Actions |

## Roadmap

- Apache Kafka for cross-service events
- AI-powered financial analytics (opsctl.ai)
- Loki + Grafana observability

## License

All rights reserved.

## Author

Kyrylo Pryiomyshev — [GitHub](https://github.com/Vilis322)
