# gateway-oss

Open-source MIT components of the Aixle Gateway.

**Status:** MVP bootstrap. Substantive code lands in later milestones.

## Scope

This repository contains the publicly licensed (MIT) Gateway components:

- **`proto/`** — Plane Protocol schema (source of truth) and pre-generated language stubs (`proto/gen/{go,python}/`).
- **`sdk/`** — Gateway SDKs for Go, Python, and TypeScript.
- **`cli/`** — `gateway-cli`, the operator command-line tool.
- **`plugins/`** — reference plug-ins:
  - `plugins/agent-platforms/` — agent-platform integrations (OpenClaw is the default reference).
  - `plugins/attestation/` — attestation provider plug-ins (SPIRE reference; free Aixle Identity verifier).
- **`configs/`** — bundled-default policy and configuration templates.
- **`examples/`** — example deployments and an engineering end-to-end client.
- **`docs/`** — public-facing Gateway documentation.

The Gateway data plane lives separately at [`lobstertrap`](https://github.com/Aixle-Corp/lobstertrap) (forked from Brex CrabTrap, also MIT). The Aixle-proprietary control plane and closed extensions live in a separate private repository.

## License

MIT — see [LICENSE](LICENSE) and [NOTICES](NOTICES).

## Building

Each language pipeline ships independently:

| Language    | Build                                | Test                                                  |
|-------------|--------------------------------------|-------------------------------------------------------|
| Go          | `go build ./...`                     | `go test ./...`                                       |
| Python      | `pip install -e .`                   | `pytest`                                              |
| TypeScript  | `cd sdk/typescript && npm install`   | `cd sdk/typescript && npm test`                       |
| Plane Protocol stubs | `./scripts/regen-proto.sh` (regenerates `proto/gen/{go,python}/`) | `proto-stub-check` workflow in CI |

## Contributing

Contribution guidelines will be added when external contributions are accepted. Until then, please file issues for bugs or feature requests; pull requests from outside the Aixle team may be held pending guideline publication.
