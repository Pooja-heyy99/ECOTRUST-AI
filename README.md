
# EcoTrust AI 🌿
### Verifiable Autonomous ESG Carbon Credit Procurement Engine

An automated environmental procurement agent wrapped within Terminal 3's secure identity framework and TEE infrastructure to enforce compliance rules, evaluate metrics, and securely block corporate greenwashing. Built for the Terminal 3 Agent Dev Kit Bounty.

## Problem
Global enterprise sustainability departments face massive regulatory liabilities and greenwashing risks when purchasing carbon offsets. While financial teams want autonomous agents to optimize marketplace buying at scale, granting blanket programmatic API keys or fund access to standard LLMs is a severe security vulnerability. Manual approvals slow deployment; unmonitored agent autonomy is unauditable and risky.

**EcoTrust AI acts as a delegated compliance buyer:** autonomous within precise corporate mandates, with every single evaluation step anchored to machine-verifiable identity proofs and immutable audit records.

## Why Verifiable Identity (Terminal 3)
* **Agent Identity (did:t3n):** Every single transaction approval is cryptographically attributable to a specific verified compliance agent handler.
* **Policy Enforcement:** Asset parameters are thoroughly parsed and validated inside an isolated TEE environment *before* payment generation can trigger.
* **Untamperable Audit Trails:** Generates verifiable compliance logs without leaking sensitive target data fields or proprietary project operational internals.

## Architecture

```text
User / Corporation ── Proposes Asset ──▶ React Frontend UI Dashboard
                                                 │
                                                 ▼
                                        POST /api/evaluate
                                                 │
                                                 ▼
                                      Fastify Guardian Server
                                                 │
                                                 ▼
                                    EcoTrustGuard (T3 SDK Client)
                                                 │
                                                 ├──▶ Efficiency Floor Check (> 45 kg/$)
                                                 ├──▶ Secure TEE Enclave Handshake
                                                 └──▶ Audit Trail → backend/output/audit-*.json


---

## Quick Start (Sandbox / Testnet Demo)

### 1. Setup the Frontend Layout Client

```bash
cd frontend
npm install
npm run dev

```

Open [http://localhost:5173/](http://localhost:5173/) on your web browser to access the dynamic enterprise dashboard interface.

### 2. Setup the Backend Guardian Node

```bash
cd backend
npm install
# Configure your credentials inside .env
node src/server.js

```

The backend node will initialize a live connection session to the Terminal 3 infrastructure.

---

## Live Integration & Environment

To connect the application engine to the live Terminal 3 network layers, copy the example environment template and populate it with your active developers parameters:

```bash
cd backend
cp .env.example .env

```

### Environment Configuration:

| Variable | Required | Purpose |
| --- | --- | --- |
| `PORT` | No | Target execution port for API server (Default: `5000`) |
| `T3N_API_KEY` | Yes | Authentic developer credentials generated from the T3 Claim Page |

---

## Project Structure

```text
ecotrust-ai/
├── backend/
│   ├── src/
│   │   ├── t3/guard.js      # Core T3 SDK Client and connection routines
│   │   └── server.js        # Fastify API router and validation guard rules
│   ├── data/                # Persistent JSON W3C Verifiable Credentials storage
│   ├── output/              # Local deterministic secure audit output records
│   ├── .env.example         # Template for safe public configuration distributions
│   └── package.json         # Dependency manifest for execution runtimes
└── frontend/
    ├── src/
    │   ├── App.jsx          # Premium UI client, console trace logs, & entry forms
    │   └── main.jsx         # Web bundler and Tailwind CSS compilation inputs
    ├── vite.config.js       # Compiler adapter configurations
    └── package.json         # UI dependency configurations

```

---

## Scripts Directory

| Command | Path | Description |
| --- | --- | --- |
| `npm run dev` | `/frontend` | Launches the interactive React + Tailwind CSS UI dashboard portal. |
| `node src/server.js` | `/backend` | Boots the Fastify API engine and fires the WebAssembly T3 handshakes. |

---

## Bounty Alignment Matrix

### 1. Completeness of Solution

EcoTrust AI features a thoroughly completed dual-layer architecture. It features a responsive graphical dashboard displaying live validation states, real-time cryptographic logs, and custom proposal entry components interacting flawlessly with an active Node.js server.

### 2. Deep SDK Integration

The platform initializes internal references using official `@terminal3/t3n-sdk` protocols, utilizing localized WebAssembly components to instantiate secure identity contexts and safely exporting execution footprints onto dedicated local storage structures.

### 3. Creative Agentic Utility

Directly addresses corporate treasury risks by introducing an autonomous filter system that evaluates and locks off matching purchases if a verified asset parameter breaches specified environmental compliance mandates.

### 4. Developer Documentation Feedback

Comprehensive technical feedback regarding PostCSS configuration steps for modern v4 project modules and ESM specifications has been cleanly structured and saved inside the dedicated `backend/docs/FEEDBACK.md` path.


# 2. Create the clean .env.example file inside your backend folder

Set-Content -Path backend/.env.example -Value 'PORT=5000
T3N_API_KEY="your_t3n_sandbox_api_key_here"'

```

```
