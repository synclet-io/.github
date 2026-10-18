# Synclet

**Run Airbyte connectors without Airbyte. One Go binary, one PostgreSQL.**

Synclet is a self-hosted, MIT-licensed control plane for connectors that implement the [Airbyte Protocol](https://docs.airbyte.com/platform/understanding-airbyte/airbyte-protocol): schema discovery, full refresh and incremental sync, scheduling and monitoring, with connectors running as Docker containers or Kubernetes pods.

- [Documentation](https://synclet-io.github.io/synclet-site/docs/getting-started/introduction/)
- [Tested with](https://synclet-io.github.io/synclet-site/docs/concepts/connectors/#tested-with): the connector images and versions run end to end, and the known issues
- [Connector licenses](https://synclet-io.github.io/synclet-site/docs/reference/connector-licenses/): connectors keep their own licenses; most Airbyte connectors are ELv2 since 2025-07-22
- [Roadmap](https://github.com/synclet-io/synclet/blob/main/ROADMAP.md)

## Quick start

```bash
git clone https://github.com/synclet-io/synclet && cd synclet && docker compose up -d
```

Open `http://localhost:8080` a minute later. The [synclet README](https://github.com/synclet-io/synclet#readme) covers secrets, Helm and production setup.

## Features

- **Airbyte Protocol connectors**: runs source and destination images that implement the Airbyte Protocol, plus MIT Go connectors
- **Execution**: Docker or Kubernetes executors, or the CLI
- **Workspaces with RBAC**: admin, editor and viewer roles for the teams of one organization
- **Secrets**: connector configuration encrypted with AES-256-GCM
- **OIDC SSO** with any OpenID Connect provider
- **Notifications**: Slack, email, Telegram and webhook alerts on sync events
- **Audit log** and YAML workspace export and import

## Repositories

| Repository | Description |
|---|---|
| [synclet](https://github.com/synclet-io/synclet) | The platform: API server, scheduler, executors and web UI |
| [connectors](https://github.com/synclet-io/connectors) | MIT Go connectors for Synclet, and the default Synclet registry (`registry.json` served via GitHub Pages) |
| [synclet-go-sdk](https://github.com/synclet-io/synclet-go-sdk) | Go SDK for writing connectors |
| [synclet-connectors-template](https://github.com/synclet-io/synclet-connectors-template) | Template for running your own connector registry |
| [synclet-connector-registry](https://github.com/synclet-io/synclet-connector-registry) | Earlier location of the Synclet registry; Synclet now uses the registry served from `connectors` |
| [synclet-site](https://github.com/synclet-io/synclet-site) | Documentation site |

## License

Synclet is MIT licensed, with every feature in the self-hosted binary. Connectors are separate images with their own licenses, see [Connector licenses](https://synclet-io.github.io/synclet-site/docs/reference/connector-licenses/).

Airbyte is a trademark of Airbyte, Inc. Synclet is not affiliated with, endorsed by or sponsored by Airbyte, Inc.
