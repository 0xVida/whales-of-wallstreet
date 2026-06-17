# Whales of Wallstreet (WOW) Monorepo

The Whales of Wallstreet (WOW) monorepo contains all core products powering the ecosystem including the marketing frontend, web app, native app and the shared backend routing engine

This structure centralizes development while keeping each product modular.



## System Overview

WOW is composed of four main components:

- Marketing Site: Public-facing product and simulation workspace
- Web App: Browser-based user interface for interacting with WOW systems
- Native App: Mobile experience built with Expo
- Wow Engine: Core backend routing, cross-chain and fiat orchestration layer

All client applications rely on Wow Engine as their shared transaction and routing backend.




## Marketing Site (Root)

The frontend marketing presence and simulation workspace for the Whales of Wallstreet ecosystem.

It demonstrates:

- Interactive protocol simulations
- Wow Engine pathfinding visualization
- Stellar anchor onboarding flows
- Ecosystem product showcases


## Wow Engine

A high-performance, modular Rust-based bridging and routing service.

It handles:

- Cross-chain token routing (Ethereum, Solana, Arbitrum to Stellar)
- Liquidity aggregation across bridge providers (Circle CCTP, deBridge DLN)
- Optimal pathfinding based on cost and execution time
- Fiat on-ramping and off-ramping via Stellar Anchors (SEP-24 and SEP-38)

### API Endpoints
- GET /api/v1/health
- POST /api/v1/quote
- POST /api/v1/anchor/deposit
- POST /api/v1/anchor/withdraw
- POST /api/v1/anchor/quote


### Tech Stack

- Rust
- Tokio
- Axum
- Reqwest



## Native App

Mobile application built with Expo.

Features:

- Unified wallet experience
- Transaction history tracking
- Deposit and withdraw flows
- Real-time balance state

### State Architecture

The app uses a global WalletProvider:

- balance: USD wallet balance
- transactions: transaction history ledger
- deposit() / withdraw(): state actions
- addTransaction(): event updates



## Web App

Browser-based application built with Vite

Provides:

- Wallet interactions
- Swap and routing UI
- Integration with Wow Engine APIs
