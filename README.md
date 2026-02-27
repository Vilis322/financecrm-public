# Finance CRM

**Enterprise-grade financial CRM for affiliate marketing operations.**

Official release: **v2.16.0** | [Live Demo](https://pryiomyshev.financecrm.dev)

> Developed by **Kyrylo Pryiomyshev**. All rights reserved.

---

## Live Demo

**[pryiomyshev.financecrm.dev](https://pryiomyshev.financecrm.dev)**

Demo environment resets daily at 3:00 UTC. Feel free to explore all features.

---

## Features

### Dynamic Role-Based Access Control

Fully dynamic permission system with 50+ permission nodes. Every module, tab, and action is independently toggleable per role or per user.

- **6 isolated permission modules**: Dashboard, Statistics, Reports, Income Journal, Expense Journal, Settings
- **Per-user overrides**: fine-tune individual permissions on top of role defaults
- **Real-time sync**: permission changes apply instantly via WebSocket — no page reload needed
- **Scope system**: Personal / Team / Company data isolation across all pages
- **Auto scope fallback**: when permissions change, the UI automatically adjusts to the highest available access level

### Financial Management

- **Income tracking**: CPL, CPA, CRG income types with per-participant FTD tracking, GEO tags, and multi-user splits
- **Expense tracking**: dynamic category parameters (text, number, date, select), team/personal expense types, split metadata
- **Multi-wallet support**: balance tracking across multiple wallets
- **Soft delete & restore**: full audit trail with deletedAt/deletedBy, one-click restore
- **Server-side pagination**: journals with accurate count and total aggregation, server-side team/member filtering

### Analytics & Reporting

- **Dashboard**: monthly summary with interactive PieChart, LineChart, team breakdown table
- **Statistics**: all-time analytics with date range, team/member, and expense class filters
- **Reports**: bidirectional profit bars, expandable team structure, income type filter, CSV export
- **Server-side aggregation**: Redis-cached statistics with automatic invalidation on data changes

### Audit System

- Complete audit trail for all CRUD operations (create, update, delete, restore, hard delete)
- Before/after change tracking stored in JSON
- Human-readable field names with full i18n support
- Separate permissions for viewing, editing, and deleting audit records

### Settings Management

- **Users**: create, edit, assign roles, reset passwords, activate/deactivate, delete
- **Teams**: create, edit, manage members, view team statistics
- **Roles**: fully dynamic role editor with hierarchical permission tree
- **Wallets**: multi-currency wallet management
- **Expense categories**: two-level hierarchy with dynamic parameters
- **Income categories & sources**: income classification with archive support

### Internationalization

3 fully translated locales: Russian, English, Ukrainian. Language preference persisted across sessions.

### Security

- JWT access + refresh tokens in httpOnly cookies
- bcrypt password hashing
- Rate limiting with optional Redis store
- Automatic idle logout with warning dialog
- Force logout via WebSocket on account changes

---

## Architecture

```
Frontend:  React 18, TypeScript, Vite, TailwindCSS, React Router, react-i18next
Backend:   Node.js, Express 5, TypeScript, Prisma ORM, Zod validation
Database:  PostgreSQL, Redis (caching + rate limiting)
Real-time: Socket.io (permission sync, force-logout, data broadcast)
Deploy:    PM2 cluster mode, Nginx, GitHub Actions CI/CD
```

### Design Principles

- **Dependency Injection** — services and repositories wired via container
- **Repository Pattern** — data access abstracted behind interfaces
- **Feature-based Modules** — each feature is a self-contained directory
- **Full Permission Isolation** — each module checks only its own permissions via `source` parameter
- **Zero-downtime Deploys** — PM2 cluster mode with graceful reload

---

## Deployment

Unified CI/CD pipeline with branch-based environment selection:

| Branch | Environment | Description |
|--------|-------------|-------------|
| `main` | Production | Safe schema sync, cluster PM2, zero-downtime reload |
| `stage` | Staging | Accepts schema changes, demo seed, fork PM2 |
| `main` | Demo | Daily reset at 3:00 UTC, demo flags enabled |

---

## License

**Proprietary Software**. All rights reserved.

Copyright (c) 2025-2026 **Kyrylo Pryiomyshev**.

For inquiries, contact via [GitHub](https://github.com/Vilis322).
