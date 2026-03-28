# FinanceCRM

Financial CRM for affiliate marketing operations — transaction tracking, expense management, ROI analytics, and team-based access control.

## Overview

FinanceCRM is a comprehensive financial management tool built for teams running large-scale advertising operations. It handles income/expense tracking across multiple wallets, per-buyer financial analytics, dynamic role-based permissions, and real-time collaboration via WebSocket.

## Features

- Multi-wallet financial tracking (crypto, fiat, payment processors)
- Income and expense management with EAV categories
- Per-buyer and per-team ROI analytics
- Dynamic RBAC with 50+ permission nodes and per-user overrides
- Real-time updates via Socket.io
- Audit trail for all financial operations
- Leads module (toggle via feature flag)
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
| CI/CD | GitHub Actions, 4 environments |

## Roadmap

- Apache Kafka for cross-service financial events
- Leads CRM extraction to standalone service (LeadCtl)
- AI-powered financial analytics (opsctl.ai)
- Loki + Grafana observability

## License

All rights reserved.

## Author

Kyrylo Pryiomyshev — [GitHub](https://github.com/Vilis322)
