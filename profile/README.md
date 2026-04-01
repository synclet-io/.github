# Synclet

**Open-source data synchronization platform built on the [Airbyte connector protocol](https://docs.airbyte.com/understanding-airbyte/airbyte-protocol).**

Connect any source to any destination with automatic schema detection, incremental sync, and real-time monitoring — all from a single Go binary.

---

## Repositories

| Repository | Description |
|---|---|
| [**synclet**](https://github.com/synclet-io/synclet) | Core platform — API server, scheduler, workers, and frontend |
| [**synclet-connector-registry**](https://github.com/synclet-io/synclet-connector-registry) | Airbyte-format connector registry served via GitHub Pages |

---

## What is Synclet?

Synclet is a **modular monolith** written in Go that runs the API server, scheduler, and sync workers as goroutines inside a single binary. It is fully compatible with the Airbyte connector protocol, meaning you can use the entire ecosystem of existing Airbyte source and destination connectors out of the box, while also supporting high-performance Go-native connectors.

**Key features:**

- 🔌 **Airbyte Protocol Compatible** — drop-in support for any Airbyte source or destination connector
- 🐳 **Multiple Execution Modes** — Docker, Kubernetes, or CLI
- 🔒 **Secrets Management** — AES-256-GCM encrypted connector configuration
- 🔐 **OIDC Authentication** — SSO with any OpenID Connect provider
- 🏢 **Workspace Isolation** — multi-tenant with role-based access control
- 🔔 **Notification Channels** — Slack, Email, and Telegram alerts on sync events
- 📊 **Dashboard & Stats** — connection health, sync timeline, records/bytes metrics
- ⚡ **Go-native Connectors** — high-performance connectors built alongside Docker-based Airbyte connectors

---

## Tech Stack

| Layer | Technologies |
|---|---|
| Backend | Go, ConnectRPC (protobuf), PostgreSQL, GORM, Uber FX |
| Frontend | Vue 3, TypeScript, TanStack Vue Query, Tailwind CSS |
| Connectors | Docker (Airbyte protocol) + Go-native (airbyte-go-sdk) |
| Orchestration | Docker (default) or Kubernetes |

---

## Quick Start

```bash
git clone https://github.com/synclet-io/synclet && cd synclet
docker compose up -d          # start PostgreSQL
cp .env.example .env          # configure environment
go run main.go migrate up     # run migrations
task dev                      # start backend with hot reload
cd front && bun install && bun run dev  # start frontend
```

See the [synclet README](https://github.com/synclet-io/synclet#readme) for the full setup guide.

---

## License

Synclet is open source. See [LICENSE](https://github.com/synclet-io/synclet/blob/main/LICENSE) in the main repository.
