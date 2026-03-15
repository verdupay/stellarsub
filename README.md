```markdown
# StellarSub

### A decentralized recurring payment protocol for subscriptions built on Stellar.

StellarSub is a decentralized subscription payment protocol that enables SaaS platforms, creators, and businesses to automate recurring payments using the Stellar network.

---

# Problem Statement

Subscription-based services power much of the modern internet, including:

- SaaS platforms
- Membership communities
- Streaming and content platforms
- Developer tools
- Digital newsletters

However, current subscription systems rely heavily on **centralized payment processors** such as Stripe or PayPal, which introduce several issues:

- High processing fees
- Limited global accessibility
- Payment censorship
- Delayed settlement
- Poor interoperability with Web3 systems

Crypto payments often lack **native recurring payment mechanisms**, making it difficult for businesses to adopt decentralized subscriptions.

---

# Solution Overview

StellarSub provides a **decentralized recurring payment protocol** that allows businesses and creators to set up automated subscription billing using the Stellar network.

Using **Soroban smart contracts**, StellarSub enables:

- Automated recurring payments
- Subscription management
- Secure authorization of payments
- Multi-asset billing (XLM and tokens)

Users authorize a subscription once, and the smart contract handles future payment execution according to the billing schedule.

---

# Key Features

### Decentralized Recurring Payments
Automated subscription payments executed via Soroban smart contracts.

### Multi-Asset Billing
Supports:

- XLM
- USDC on Stellar
- Custom Stellar tokens

### Subscription Management
Users can:

- Create subscriptions
- Pause subscriptions
- Cancel subscriptions
- View payment history

### Merchant Subscription Dashboard
Businesses can monitor:

- Active subscribers
- Payment cycles
- Revenue analytics

### Permission-Based Payments
Users approve recurring payment limits without giving full custody.

### Transparent Smart Contracts
All subscription rules are enforced on-chain.

### Developer-Friendly APIs
Easy integration for SaaS platforms and Web3 apps.

---

# How It Uses Stellar

StellarSub leverages key components of the Stellar ecosystem.

**Soroban Smart Contracts**

- Manage subscription agreements
- Schedule recurring payments
- Enforce billing logic

**Stellar SDK**

- Build and sign transactions
- Interact with Soroban contracts

**Horizon API**

- Monitor payments
- Query transaction history
- Fetch account balances

**Stellar Assets**

Supports subscriptions paid with:

- XLM
- USDC
- Custom tokenized assets

---

# Architecture Overview

```

```
        User / Subscriber
              │
              ▼
        Frontend dApp
       (Subscription UI)
              │
              ▼
        Backend API
    (Subscription Manager)
              │
              ▼
       Soroban Contracts
  (Recurring Payment Logic)
              │
              ▼
       Stellar Network
              │
              ▼
        Horizon API
    (Transaction Monitoring)
```

````

Core modules:

- Subscription Registry
- Payment Scheduler
- Merchant Dashboard
- Contract Interaction Layer

---

# Tech Stack

**Frontend**

- React
- Next.js
- TailwindCSS

**Backend**

- Node.js
- Express.js

**Blockchain Integration**

- Stellar SDK
- Soroban Smart Contracts
- Horizon API

**Database**

- PostgreSQL

**Infrastructure**

- Docker
- Cloud deployment (AWS / Vercel)

---

# Installation Guide

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/stellarsub.git
cd stellarsub
````

---

### 2. Install dependencies

```bash
npm install
```

---

### 3. Configure environment variables

Create `.env` file.

```
STELLAR_NETWORK=testnet
HORIZON_URL=https://horizon-testnet.stellar.org
SOROBAN_RPC_URL=https://soroban-testnet.stellar.org
DATABASE_URL=postgresql://user:password@localhost:5432/stellarsub
PORT=4000
```

---

### 4. Deploy Soroban contracts

```bash
stellar contract deploy \
--wasm target/wasm32-unknown-unknown/release/subscription_contract.wasm \
--network testnet
```

---

### 5. Start the application

```bash
npm run dev
```

---

# Usage Example

### Create a Subscription

Merchant defines a subscription plan.

```
Plan Name: Pro Membership
Price: 10 USDC
Billing Cycle: Monthly
```

User subscribes via wallet approval.

```
Approve recurring payment: 10 USDC every 30 days
```

---

### Automatic Payment Execution

When the billing cycle arrives:

```
Soroban contract triggers payment
10 USDC transferred to merchant wallet
Transaction confirmed on Stellar
```

User receives confirmation.

---

# API Overview

### Create Subscription Plan

```
POST /api/subscriptions/create
```

Request

```json
{
  "merchant_id": "merchant123",
  "plan_name": "Pro Plan",
  "price": "10",
  "asset": "USDC",
  "billing_cycle_days": 30
}
```

---

### Subscribe to Plan

```
POST /api/subscriptions/subscribe
```

Response

```json
{
  "status": "active",
  "next_payment": "2026-04-15",
  "plan": "Pro Plan"
}
```

---

# Roadmap

### Phase 1

* Basic Soroban subscription contract
* XLM recurring payments
* Simple merchant dashboard

### Phase 2

* Multi-asset support
* Wallet integrations
* Payment notifications

### Phase 3

* Advanced subscription analytics
* Payment retry logic
* Cross-platform SDKs

### Phase 4

* Decentralized subscription marketplace
* DAO-based subscription services
* Global merchant integrations

---

# Potential Impact on the Stellar Ecosystem

StellarSub introduces a missing primitive in the Stellar ecosystem: **decentralized recurring payments**.

This enables:

* SaaS platforms to accept Stellar subscriptions
* Content creators to monetize audiences
* DAOs to manage membership payments
* Developers to build subscription-based Web3 apps

The protocol can significantly increase **transaction volume and utility** on the Stellar network.

---

# Future Improvements

* Cross-chain subscription payments
* Wallet-native subscription approvals
* Payment retry automation
* NFT-based subscription passes
* Creator monetization tools
* Subscription analytics dashboard

---

# License

MIT License

Copyright (c) 2026 StellarSub

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files to deal in the Software without restriction.

```
```
