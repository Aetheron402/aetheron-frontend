# Aetheron Frontend

Public UI for the **Aetheron X402 Component Marketplace** and the broader **Aetheron ecosystem**.

---

## Overview

This repository contains the **public-facing frontend** for Aetheron.

It provides the user interface for:

- Browsing pay-per-use AI components  
- Connecting a Solana wallet (Phantom)  
- Selecting USDC or AETH as a payment method  
- Triggering X402-style payment-required flows  
- Manually submitting on-chain payments  
- Pasting transaction signatures for verification  
- Submitting component execution requests  
- Tracking job status and downloading generated outputs  
- Browsing and purchasing prebuilt automation agent templates  
- Reading the Aetheron Litepaper (Docs V2) and protocol documentation  
- Viewing ecosystem, roadmap, and token information  

The frontend is intentionally **lightweight, static, and framework-agnostic**, with all critical enforcement handled server-side.

---

## Important Note

This repository contains **frontend UI code only**.

It does **not** include:

- Backend APIs or worker logic  
- On-chain payment verification  
- Transaction validation or replay protection  
- AI prompts or inference logic  
- PDF / DOCX / TXT / HTML / Markdown generation  
- AETH pricing or oracle logic  
- Ledger, billing, or accounting systems  
- Agent source code or proprietary templates  

All operational logic exists in a **private backend** and is not exposed here.

This repository is safe for public visibility.

---

## Documentation (Docs V2)

The frontend includes a public **Learn / Litepaper** section (Docs V2) that provides
a technical overview of the Aetheron protocol.

It covers:

- X402 payment flow and execution model  
- Component architecture and constraints  
- On-chain verification and provenance  
- Pseudocode examples and protocol behavior  
- Wallet usage and $AETH utility  

The documentation is informational only and does not expose backend logic.

---

## Core Concepts

### X402 Payment Flow (Manual)

Aetheron uses a **manual X402-style payment-required flow**.

1. The user initiates a component or agent request  
2. The backend responds with `402 Payment Required`  
3. The frontend displays:
   - Destination wallet address  
   - Required payment amount (USDC or AETH)  
4. The user manually submits an on-chain transaction using their wallet  
5. The user pastes the transaction signature into the interface  
6. The backend verifies the transaction on-chain  
7. The request is accepted, queued, or fulfilled  

The frontend **does not construct, sign, or submit transactions** and never has access to private keys.

All payment enforcement and verification occurs server-side.

---

## Component Types

### Pay-Per-Use AI Components
- Prompt Optimizer  
- Code Explainer  
- Prompt Tester (PersonaSim)  
- Contract Intelligence Analyzer  

These generate **user-specific outputs** (PDF, TXT, DOCX, HTML, MD) and are tracked via the backend ledger.

### Prebuilt Agent Templates
- Large downloadable ZIP templates  
- Desktop-only by design  
- Not stored in the user asset library  
- Intended as one-time licensed downloads  

Agents are intentionally **not treated as ledger assets** to avoid mobile UX issues and excessive storage coupling.

---

## Tech Stack

- HTML + Jinja2 templates  
- TailwindCSS  
- Vanilla JavaScript  
- Phantom Wallet (address connection only)  
- Manual Solana SPL payments (USDC + AETH)  
- Backend-enforced X402-style payment verification  

No frontend frameworks or client-side signing libraries are used.

---

## Backend (Private)

The frontend communicates with a **private FastAPI backend**, which handles:

- Solana on-chain payment verification  
- USDC & AETH routing and tolerance checks  
- Partial payment handling  
- Replay protection  
- Job dispatching via Celery  
- AI processing and report generation  
- Secure file delivery (R2 / S3-compatible storage)  
- Rate limits, validation, and security enforcement  

The backend is closed-source by design.

---

## Project Structure

```
/static
   /css
   /js
/templates
   base.html
   shop.html
   agents.html
   learn.html
   component modals
   token & roadmap pages
```

All pages extend a shared base layout and wallet integration layer.

---

## Wallet Support

- **Solana (Phantom)** — supported  
- **Ethereum (MetaMask)** — planned (Q1 2026)

Wallet state is shared globally across pages via the base template.

---

## SDK

Aetheron provides a **public TypeScript SDK** for developers who want to integrate
Aetheron components directly into their own applications without using the web UI.

The SDK supports **manual and programmatic X402-style payment flows**, depending on integration context.

The web frontend currently uses a **manual payment + signature submission model**.

**Repository:** https://github.com/Aetheron402/aetheron-sdk  

The SDK is optional and not required to use this frontend.

---

## Links

- **Website:** https://www.aetheron402.com  
- **X / Twitter:** https://twitter.com/Aetheron402  
- **Email:** team@aetheron402.com  

---

<p align="center"><sub>Part of the Aetheron ecosystem — execution powered by X402.</sub></p>

