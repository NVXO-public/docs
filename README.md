# NVXO Ecosystem — Technical Documentation

> Public technical reference for the NVXO ecosystem. Smart contract implementation is proprietary. This repository contains architecture specifications, API references, and interface definitions.

## Contents

```
docs/
├── architecture/
│   ├── overview.md              # System-wide architecture
│   ├── core-infrastructure.md  # NVXO Chain, bridge, API gateway
│   ├── cex.md                  # Centralized exchange architecture
│   ├── dex.md                  # DEX / AMM architecture
│   ├── wallet.md               # Wallet & messaging architecture
│   ├── pay.md                  # Neobanking architecture
│   ├── tokenization.md         # RWA tokenization architecture
│   └── compliance.md           # AI & compliance engine
├── api/
│   ├── openapi.yaml            # Full OpenAPI 3.0 specification
│   └── websocket.md            # WebSocket stream documentation
├── token/
│   ├── tokenomics.md           # NVXO token economics
│   └── governance.md           # DAO governance specification
└── security/
    └── security-model.md       # Security architecture overview
```

## Quick Links

| Document | Description |
|----------|-------------|
| [Architecture Overview](architecture/overview.md) | System-wide technical architecture |
| [Core Infrastructure](architecture/core-infrastructure.md) | NVXO Chain + Bridge + API Gateway |
| [OpenAPI Specification](api/openapi.yaml) | Full REST API reference |
| [Token & Governance](token/tokenomics.md) | NVXO tokenomics and DAO governance |
| [Security Model](security/security-model.md) | Security architecture and audit status |

## NVXO Chain — Key Specs

| Property | Value |
|----------|-------|
| Consensus | Delegated Proof-of-Stake (DPoS) |
| Block Time | 1.5 seconds |
| Throughput | 10,000 TPS |
| EVM Compatible | Yes — Solidity 0.8.x |
| Gas Token | NVXO |
| Validators | 21 active + 100 standby |
| Bridge | ETH, BSC, Polygon, Solana, TRON |

## Smart Contract Audits

Planned audits: **CertiK** (token + governance) · **Halborn** (bridge + infrastructure) · **Trail of Bits** (DEX + marketplace)

Published reports will appear in [audit-reports](https://github.com/NVXO-public/audit-reports).

## API Base URL

```
https://api.nvxo.io/v1
```

Authentication: `Authorization: Bearer <api_key>`

Full OpenAPI 3.0 spec: [api/openapi.yaml](api/openapi.yaml)

---

*For integration support contact: dev@nvxo.io*
