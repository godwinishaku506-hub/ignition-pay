# Ignition Pay 🔥

## What is Ignition Pay?

Ignition Pay is a **full-stack, cross-platform Stellar wallet** built with Dart and Flutter — delivering a native-grade payment experience on Android, iOS, and web from a single codebase.

A unified wallet ecosystem that combines:

- **Stellar asset management** — send, receive, and manage XLM and Stellar-issued assets with ease
- **Stablecoin payments** — native USDC on Stellar, with seamless anchor integrations for fiat on/off ramps
- **Smart contract interactions** — Soroban-powered payment flows, right from your pocket
- **Developer-ready API** — a clean Dart backend powering everything under the hood

Most wallets are thin clients. Ignition Pay is a full product — from the Dart API layer handling blockchain logic, to the Flutter UI your users will actually love.

---

## The Problem

Stellar is one of the fastest, cheapest blockchain networks in existence — yet wallets that do it justice are rare.

Most Stellar wallets are web-only, clunky, or built for developers rather than real users. Mobile experiences are an afterthought. Stablecoin and anchor workflows are buried behind complex steps. And building on top of Soroban smart contracts still requires stitching together multiple incompatible libraries.

**Ignition Pay changes that.**

---

## What It Does

**Pay and get paid — everywhere.**
Send and receive XLM, USDC, and any Stellar-issued asset instantly. Full trustline management, account funding, and transaction history — all from a Flutter app that feels native on every platform.

**Fiat in, fiat out.**
Deep anchor integrations via the SEP-6, SEP-24, and SEP-31 standards. Deposit and withdraw real money through regulated anchors without ever leaving the app. No browser redirects. No broken flows.

**Soroban in your hands.**
Invoke Soroban smart contracts directly from the mobile client. The Dart API layer handles encoding, signing, and submission — your users just tap a button.

**API-first architecture.**
A Dart backend (built with Shelf or Dart Frog) handles wallet logic, key management, anchor communication, and Horizon API calls. The Flutter app is just a clean consumer of that API.

**Vote with proof.**
A blockchain-powered governance layer where every vote is verifiable and every result is permanent. Communities can participate in on-chain decisions — real engagement, zero manipulation.

---

## Tech Stack

```
Mobile & Web     Flutter · Dart · Material 3 / Custom Design System
Backend API      Dart · Shelf / Dart Frog · REST + WebSocket
Blockchain       Stellar SDK for Dart · Soroban RPC · Horizon API
Auth             Stellar keypair signing · JWT sessions · Biometric unlock
Database         PostgreSQL · Drift ORM (Dart-native)
Real-time        WebSockets · Stellar event streaming via Horizon SSE
SEP Standards    SEP-6 · SEP-10 · SEP-24 · SEP-31 · SEP-38
```

---

## Architecture

```
ignition-pay/
│
├── apps/
│   └── mobile/             ← Flutter — iOS, Android & Web
│                              Wallet UI, asset management,
│                              payment flows, Soroban UI
│
├── services/
│   └── api/                ← Dart (Shelf / Dart Frog)
│                              REST API, WebSocket gateway,
│                              Horizon proxy, anchor orchestration,
│                              key custody layer, JWT auth
│
├── contracts/
│   └── soroban/            ← Rust — Soroban smart contracts
│                              compiled to WASM, deployed on Stellar
│
└── packages/
    └── ignition_core/      ← Shared Dart package
                               Stellar SDK wrappers, SEP clients,
                               transaction builders, type definitions
```

Each layer owns one responsibility. The Flutter app talks to the Dart API. The API coordinates with Horizon and Soroban RPC. The Rust contracts execute on-chain. Clean, auditable, and independently deployable.

---

## Mobile-First Design

Ignition Pay is built mobile-first, not mobile-ported.

- **Biometric authentication** — FaceID, fingerprint, and device PIN via Flutter's `local_auth`
- **Deep link support** — open payment requests directly from links or QR scans
- **Offline-resilient** — transaction drafts survive no-network moments, submitted when connectivity returns
- **Push notifications** — real-time payment alerts via FCM, powered by Horizon SSE on the API side
- **Adaptive UI** — one Flutter codebase that looks intentional on phones, tablets, and browsers

---

## Anchor & SEP Integration

Fiat corridors are first-class citizens in Ignition Pay.

| Standard | Purpose |
|----------|---------|
| SEP-10   | Stellar Web Authentication — anchor login |
| SEP-24   | Interactive deposit & withdrawal flows |
| SEP-6    | Non-interactive transfers via API |
| SEP-31   | Cross-border direct payments |
| SEP-38   | Anchor RFQ — get quotes before you send |

The Dart API layer handles all SEP orchestration, so the Flutter app only ever deals with clean, typed response models.

---

## Why Ignition Pay

**Real mobile, not a wrapper.**
Flutter gives Ignition Pay true native performance — 60fps animations, platform-specific gestures, and OS-level integrations — not a WebView in disguise.

**Dart end to end.**
Your backend and your app share the same language, the same types, and the same `ignition_core` package. No context switching. No SDK mismatches. One team can own the whole stack.

**Stellar-native by design.**
Built around Stellar's unique strengths — near-zero fees, 5-second finality, built-in order book, and a rich anchor ecosystem. Not a generic crypto wallet retrofitted for Stellar.

**It compounds across layers.**
The stablecoin payment infrastructure powers in-app economies. The governance layer lets communities direct the roadmap. The developer tooling accelerates everything built on top. Each piece makes the others stronger.

**Open and auditable.**
Every contract is on-chain. Every API is open-source. No admin backdoors. No closed key infrastructure. Your keys, your funds.

**Built for real adoption.**
Near-zero fees on Stellar make micro-payments viable. The Dart API removes blockchain complexity from the Flutter client. Real people can actually use Ignition Pay without understanding what a gas fee is.

---

## Getting Started

**Prerequisites:** Flutter `3.22+`, Dart `3.4+`, Rust `1.74+`, PostgreSQL, `wasm32-unknown-unknown` target

```bash
# Clone the repository
git clone https://github.com/your-org/ignition-pay.git
cd ignition-pay

# Install Flutter dependencies
cd apps/mobile && flutter pub get

# Install API dependencies
cd ../../services/api && dart pub get

# Install shared package
cd ../../packages/ignition_core && dart pub get

# Configure environment
cp .env.example .env
# Add: HORIZON_URL, SOROBAN_RPC_URL, DATABASE_URL, JWT_SECRET

# Run the API server
cd services/api && dart run bin/server.dart

# Run the Flutter app
cd apps/mobile && flutter run
```

---

## Core Principles

**Mobile-first, always** — if it doesn't work beautifully on a phone, it doesn't ship.

**Dart as the backbone** — a unified language across API and app means faster iteration and fewer integration bugs.

**Stellar-native** — leverage everything Stellar offers: anchors, order books, Soroban, and sub-cent fees.

**SEP-compliant by default** — interoperability with the anchor ecosystem is a requirement, not a feature.

**Non-custodial where it matters** — users control their keys. The API never holds private keys in production.

**Cross-chain by design** — the future is multi-chain. Ignition Pay is built for that reality from day one.

**Community-owned** — the roadmap belongs to the people building with and using Ignition Pay.

---

## Roadmap

- [ ] Hardware wallet support (Ledger via BLE)
- [ ] Soroban dApp browser
- [ ] Multi-account & watch-only wallets
- [ ] Stellar DEX trading interface
- [ ] iOS & Android app store release
- [ ] In-app anchor onboarding wizard
- [ ] On-chain governance voting UI
- [ ] Cross-chain stablecoin bridge (USDC, USDT, DAI)

---

## Contributing

Ignition Pay is open source and welcomes contributors. See `CONTRIBUTING.md` for guidelines on submitting issues, proposing features, and opening pull requests.

---

## License

MIT License — see `LICENSE` for details.
