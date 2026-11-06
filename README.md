# SkyWorld Stall — Backend (shared API)

Iisang backend para sa **store**, **owner**, **admin**, at **operator** frontends.

Lahat ng sales, inventory, accounts, at reports ay naka-store dito (SQLite). Kapag may order sa store, automatic na makikita sa owner dashboard at ma-u-update ang sales ng stall.

## Requirements

- Node.js **≥ 22.5**
- Walang external npm packages (pure Node)

## Quick start

```bash
cd backend
cp .env.example .env
# i-edit ang .env — lalo na ALLOWED_ORIGINS
npm start
# API: http://localhost:3000
```

Seed / reset demo data:

```bash
npm run seed
npm run seed:reset
```

## Environment

| Variable | Purpose |
| --- | --- |
| `PORT` | Default `3000` |
| `APP_ORIGIN` | Public URL ng backend |
| `ALLOWED_ORIGINS` | Comma-separated frontend URLs (CORS + cookies) |
| `TRUST_PROXY` | `1` kung nasa Render/Railway/Nginx |
| `DB_PATH` | Default `data/skyworld.db` |

Halimbawa production `.env`:

```env
NODE_ENV=production
PORT=3000
APP_ORIGIN=https://api.yourdomain.com
ALLOWED_ORIGINS=https://store.yourdomain.com,https://owner.yourdomain.com,https://admin.yourdomain.com,https://operator.yourdomain.com
TRUST_PROXY=1
RESET_PEPPER=long-random-secret
```

## Deploy suggestions

- **Render / Railway / Fly.io / any Node VPS**
- Persist the `data/` folder (database + uploads)
- Expose only the API port; frontends are separate static hosts

## Demo accounts (seed)

| Role | Email | Password |
| --- | --- | --- |
| Admin | admin@skyworld.ph | Admin@123 |
| Operator | operator@skyworld.ph | Operator@123 |
| Owner | owner@skyworld.ph | Owner@123 |

Bagahin o tanggalin bago production.
