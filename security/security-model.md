# Security Architecture

## Overview

NVXO applies a defence-in-depth security model across all layers: blockchain consensus, smart contracts, custody, API, and compliance.

## Layers

### 1. Blockchain Layer
- **Consensus:** DPoS with 21 active validators
- **Slashing:** 5% for double-sign · 0.5% for liveness faults
- **Validator Keys:** HSM hardware + MPC — no single point of compromise
- **Sentry Nodes:** 2 per validator for DDoS protection
- **Geographic Distribution:** Validators required in 3+ regions

### 2. Smart Contract Layer
- **Audit:** Dual audit — CertiK + Halborn (bridge) + Trail of Bits (DEX)
- **Formal Verification:** Bridge contracts via Certora
- **Proxy Pattern:** UUPS upgradeable with timelock delay
- **Bug Bounty:** Immunefi programme
- **Re-entrancy Guard:** OpenZeppelin ReentrancyGuard on all state-changing functions
- **Emergency Pause:** Admin multisig circuit breaker on all critical contracts

### 3. Custody Layer (CEX)
| Storage Tier | % of Funds | Protection |
|-------------|------------|------------|
| Cold | >80% | Air-gapped · geographically distributed |
| Warm | ~15% | Multi-sig 3-of-5 |
| Hot | <5% | HSM-protected |

- MPC (Multi-Party Computation): private key never assembled in one place
- Withdrawal whitelist with mandatory 24h freeze on new addresses
- Scheduled signing windows (every 4–6 hours)

### 4. Wallet Layer
- BIP-44 HD wallet — 12/24-word BIP-39 mnemonic
- Biometric auth (Face ID / Touch ID) + 6-digit PIN
- Duress PIN — shows empty wallet under coercion
- AES-256 encrypted optional cloud backup
- Auto-lock after configurable inactivity period
- Token approval revoke manager built-in

### 5. Bridge Layer
- 9-of-15 multisig validator set
- zk-SNARK proof of source chain state
- Formal verification via Certora
- 3-of-5 emergency committee pause capability
- Bridge insurance fund (2% of fees accrued)

### 6. API & Infrastructure Layer
- Zero-trust internal network architecture
- IP whitelist per API key
- OAuth 2.0 + JWT authentication
- Rate limiting + DDoS protection (Cloudflare + WAF)
- TLS 1.3 in transit · AES-256 at rest
- SOC 2 Type II annual compliance audit
- Quarterly penetration testing by external red team
- 24/7 on-call security team — <15 minute response SLA

### 7. Compliance Layer
- Real-time AML screening on every transaction (all modules)
- Chainalysis + Elliptic blockchain analytics
- FATF Travel Rule: Notabene / Sygna integration
- Regulatory coverage: FATF · MiCA · 6AMLD · FinCEN · FCA · BaFin

## Security Council

A 5-of-9 Security Council holds emergency action capability:
- Can pause protocol contracts
- Can pause bridge
- Cannot access user funds
- Actions are time-locked where possible

## Incident Response

| Level | Trigger | Response Time | Action |
|-------|---------|--------------|--------|
| P0 Critical | Active exploit / fund risk | <15 min | Emergency pause + Security Council |
| P1 High | Vulnerability confirmed | <2 hours | Patch + coordinated disclosure |
| P2 Medium | Suspicious activity | <24 hours | Investigation + monitoring |
| P3 Low | Bug report | <72 hours | Standard patch cycle |

## Audit Status

| Scope | Auditor | Status |
|-------|---------|--------|
| Token + Vesting Contracts | CertiK | Planned Q3 2025 |
| Bridge Protocol | Halborn + independent | Planned Q3 2025 |
| DEX Smart Contracts | Trail of Bits / Quantstamp | Planned Q4 2025 |
| Tokenization (ERC-1400) | CertiK + Halborn | Planned Q4 2025 |

Published reports: [audit-reports repository](https://github.com/NVXO-public/audit-reports)
