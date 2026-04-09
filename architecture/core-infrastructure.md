# Core Infrastructure

## NVXO Chain

| Spec | Value |
|------|-------|
| Chain ID | `nvxo-mainnet-1` |
| Consensus | Delegated Proof-of-Stake (DPoS) |
| Block Time | 1.5 seconds |
| Throughput | 10,000 TPS |
| Gas Token | NVXO |
| EVM Compatible | Yes — 100% |
| Smart Contract Language | Solidity 0.8.x |
| Validator Bond | 1,000,000 NVXO staked |
| Active Validators | 21 (+ 100 standby) |
| Slashing | 5% double-sign · 0.5% liveness |
| Average Gas Fee | < $0.01 |
| Native Bridge | Built-in to Ethereum mainnet |
| Client Software | go-nvxo (open-source geth fork) |

### Validator Node Requirements

| Node Type | Role | Min Spec |
|-----------|------|----------|
| Validator | Core consensus | 32 vCPU · 128 GB RAM · 4 TB NVMe |
| Sentry | DDoS protection | 2 recommended per validator |
| Archive | Full history | High-storage |
| RPC | Public API | Rate-limited |

### Validator Rewards & Slashing

- Block rewards + gas fees distributed pro-rata per block
- Stake-weighted election — top 21 by delegated stake enter active set
- 99.5% uptime required to remain in active set
- Geographic distribution: validators required in 3+ regions

## Bridge Protocol

| Feature | Detail |
|---------|--------|
| Supported Chains | ETH · BSC · Polygon · Solana · TRON |
| NFT Bridge | ERC-721 · ERC-1155 → ETH, Polygon, NVXO Chain |
| Security Model | 9-of-15 multisig + zk-SNARK state proof |
| Transfer Time | < 3 minutes |
| Fee | 0.05%–0.1% in source chain gas token |
| Messaging Layer | LayerZero |
| Emergency Pause | 3-of-5 security committee |
| Insurance Fund | 2% of bridge fees accrued |
| Audit | Halborn + independent auditor |

### Bridge Routes

| From | To | Assets | Avg Time |
|------|----|--------|----------|
| NVXO Chain | Ethereum | ETH, USDT | ~5 min |
| NVXO Chain | BSC | BNB, USDT | ~3 min |
| Ethereum | NVXO Chain | ETH, USDC | ~8 min |
| Arbitrum | NVXO Chain | ETH, USDC | ~2 min |
| BSC | Polygon | BNB, USDT | ~4 min |

## API Gateway

| Feature | Detail |
|---------|--------|
| Base URL | `https://api.nvxo.io` |
| Protocols | REST · WebSocket · GraphQL · FIX 4.2 |
| Auth | API Key · OAuth 2.0 · JWT |
| Versioning | v1, v2 — 12-month deprecation notice |
| SDKs | JavaScript/TypeScript · Python · Go · Java |
| Sandbox | Full testnet — free developer access |
| Webhooks | Order fill · deposit · withdrawal events |

## Developer Tools

| Tool | Description |
|------|-------------|
| NVXO CLI | Command-line interface (Go) |
| Hardhat Plugin | Deploy/test on NVXO Chain |
| Foundry Support | Rust-based testing + deployment |
| Subgraph Template | The Graph starter for NVXO Chain |
| Remix Integration | Deploy from browser IDE |
| OpenZeppelin | All OZ contracts compatible |
| Bug Bounty | Immunefi — up to $500K reward |
| Testnet | Public testnet + faucet — free |
