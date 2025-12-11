# Aetheron Frontend

Public UI for the **Aetheron X402 Component Marketplace** and **Aetheron Token ecosystem**.

---

## Overview

This repository contains the **public-facing frontend** for Aetheron.  
It provides the interface for:

- Browsing AI components  
- Wallet authentication (Phantom → MetaMask coming Q1 2026)  
- Triggering X402 on-chain payments  
- Submitting component requests to the backend  
- Showing generated outputs (PDF, TXT, DOCX, MD, HTML)  
- Accessing the Aetheron Token page  
- Purchasing downloadable agent templates (Agent Store)  

The frontend is fully static, lightweight, and framework-agnostic.

---

## Important Note

This repository contains **UI code only**.  
It does **not** include:

- Backend or worker logic  
- Payment verification or validation  
- Component engines  
- PDF/MD/TXT renderers  
- AETH price calculations  
- AI prompts or processing logic  
- Any proprietary intelligence systems  

All operational logic exists in the private backend.

This repo is safe for public visibility.

---

## Tech Stack

- HTML & Jinja2 templates  
- TailwindCSS  
- Vanilla JavaScript  
- Solana Web3.js (Phantom)  
- Token-2022 SPL integration  
- Secure CSP headers  
- X402 on-chain triggers (USDC + AETH)  

---

## Backend (Private)

The frontend communicates with the private backend, which handles:

- On-chain payment verification  
- USDC and AETH price routing  
- Worker task creation (Celery)  
- PDF/TXT/DOCX/HTML/MD generation  
- Agent ZIP packaging  
- Ledger & billing entries  
- R2 (S3) storage uploads  
- Rate limits, validation, and security  

The backend remains closed-source for product protection.

---

## Project Structure

```
/static
   /css
   /js
/templates
   base.html
   component pages
   agent store
   token page
```

---

## SDK

Aetheron provides a public **TypeScript SDK** for wallet-native integration:

- USDC / AETH payments  
- Component generation  
- Wallet-adapter support  

(Repository: aetheron-sdk — coming soon)

---

## Links

- **Website:** https://www.aetheron402.com  
- **X / Twitter:** https://twitter.com/Aetheron402  
- **Email:** team@aetheron402.com  

---

<p align="center"><sub>Part of the Aetheron AI ecosystem — powered by X402.</sub></p>
