# 🤖 AI Migration Platform

> An intelligent, developer-centric software engineering platform designed to automate third-party API breaking change migrations.

---

## 🌟 Key Features

- **GitHub OAuth Authentication**: Secure OAuth flow for authenticating developers and managing GitHub repositories without Personal Access Tokens (PATs).
- **API Provider Connectors**: Modular connectors monitoring **OpenAI API** (`v0.28` → `v1.x+` breaking changes) and **Stripe API** (Charges → PaymentIntents migration).
- **API Version Comparison Engine**: Computes exact version deltas and breaking change matrices between repository manifests and active provider releases.
- **Documentation Intelligence**: Extracts structured migration rules, documentation reference URLs, and replacement hints from official changelogs and migration guides.
- **Language-Aware Repository Scanner**: Scans source code files (`.py`, `.js`, `.ts`) and dependency manifests (`package.json`, `requirements.txt`) for legacy API invocations.
- **Multi-Factor AI Migration Engine**: Combines official documentation rules + repository code context + version delta matrix + Google Gemini 1.5/2.0 Flash LLM reasoning to compute a **Multi-Factor Confidence Score (0-100%)**.
- **Streamlined Validation Pipeline**: Verifies AST syntax compilation, dependency compatibility, and static secret key safety before opening PRs.
- **GitHub Pull Request Generator**: Creates git branches, commits updated code diffs, and opens rich GitHub Pull Requests containing evidence breakdowns, documentation links, and validation reports.
- **Developer Web Portal**: Sleek, modern developer dashboard inspired by Vercel, Linear, and GitHub dark mode themes, complete with a side-by-side code diff viewer.

---

## 🛠️ Architecture Overview

```
GitHub OAuth / Developer
        │
        ▼
Repository Connector Module (Octokit API)
        │
        ▼
Language-Aware Repository Scanner
        │
        ▼
API Provider Connectors (OpenAI & Stripe)
        │
        ▼
API Version Comparison Engine
        │
        ▼
Documentation Intelligence Engine
        │
        ▼
AI Migration Engine (Multi-Factor Evidence + Gemini Flash)
        │
        ▼
Validation Pipeline (Syntax + Dependencies + Secret Key Check)
        │
        ▼
GitHub Pull Request Generator
```

---

## 🚀 Quick Start Guide

### Prerequisites
- Node.js v18+ or Docker Desktop
- Google Gemini API Key (Optional, fallback rule-based transformer included)

### 1. Installation
```bash
# Clone the repository and install all dependencies
npm run setup
```

### 2. Configure Environment Variables
Copy `.env.example` to `.env`:
```bash
cp .env.example .env
```

### 3. Run Locally (Development Mode)
```bash
# Starts Express Backend (Port 5000) & React Vite Frontend (Port 5173) concurrently
npm run dev
```

### 4. Run via Docker Compose (Optional Deployment)
```bash
npm run docker:up
```

---

## 🧪 Running Automated Tests

```bash
npm test
```

Verifies:
- Scanner pattern detection on legacy OpenAI & Stripe code.
- Validation engine syntax parsing and secret scanner.
- AI Migration Engine multi-factor confidence score calculation.

---

## 📚 System Documentation
- [System Architecture](docs/ARCHITECTURE.md)
- [User Guide](docs/USER_GUIDE.md)
- [Developer & Extensibility Guide](docs/DEVELOPER_GUIDE.md)
