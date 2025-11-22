<h1 align="center">Aetheron Frontend</h1>

<p align="center">
  User interface for the Aetheron X402 Component Marketplace.
</p>

---

## 🌐 Overview

This repository contains the **public-facing frontend** for the Aetheron platform.  
It is responsible for:

- Displaying available AI components  
- Handling wallet connections (Phantom today, MetaMask in Q1 2026)  
- Rendering component modals & inputs  
- Submitting requests to the backend  
- Showing generated results to users  
- UI for the Aetheron Token, Ledger, Roadmap, and Component pages

The frontend is built using lightweight, fully static web technologies.

---

## 🛠 Tech Stack

- HTML / Jinja2 Templates  
- TailwindCSS  
- JavaScript  
- Solana Web3 Wallet Adapter  
- Static asset delivery  
- X402 payment triggers (Solana → USDC)

---

## 🔌 Backend

This frontend interacts with the private backend service:

- Payment validation  
- Task creation  
- Celery worker pipeline  
- File generation (PDF / TXT)  
- Asset storage & history tracking  

Backend is private to protect proprietary logic.

---

## 🗂 Project Structure

/static
   /css
   /js
/templates
/generated

---

## 🌐 Links

- **Main Website:** https://www.aetheron402.com  
- **Twitter:** https://twitter.com/Aetheron402  
- **Email:** team@aetheron402.com  

---

<p align="center">
  <sub>Part of the Aetheron AI ecosystem — powered by X402.</sub>
</p>
