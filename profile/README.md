<div align="center">

# 🧉 M.A.T.E.
### Modern AI Testing Ecosystem · Model-Agnostic Test Engineering

**Transform generic AI coding assistants into elite, deterministic Software Development Engineers in Test (SDETs).**

[![npm version](https://img.shields.io/npm/v/mate-sdt?color=CB3837&style=flat-square)](https://www.npmjs.com/package/mate-sdt)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Playwright](https://img.shields.io/badge/Playwright-v1.50+-45ba4b?style=flat-square&logo=playwright&logoColor=white)](https://playwright.dev/)
[![GitHub stars](https://img.shields.io/github/stars/mate-sdt/mate-sdt?style=flat-square)](https://github.com/mate-sdt/mate-sdt/stargazers)

<br/>

[**Quickstart**](#-quick-start) •
[**Why M.A.T.E.?**](#-why-mate) •
[**The 4 Pillars**](#-core-pillars) •
[**16 Specialized Skills**](#-the-16-skills-ecosystem) •
[**Repositories**](#-ecosystem-repositories) •
[**Manifesto**](https://github.com/mate-sdt/mate-sdt/blob/main/MANIFESTO.md) •
[**Support**](https://ko-fi.com/crespoantonio)

</div>

---

## 💡 What is M.A.T.E.?

Frontier AI reasoning models (**Claude Sonnet & Opus 5.5**, **OpenAI GPT-6 / GPT-5.6 series**, **Google Gemini 4**, and **DeepSeek V4**) and autonomous coding environments (**Claude Code**, **Cursor**, **Windsurf**, **Google Antigravity**, **GitHub Copilot**, and **OpenAI Codex CLI**) are extraordinary at algorithmic problem-solving, architectural reasoning, and feature development. 

However, when tasked with **Software Quality & End-to-End Test Automation**, even the most advanced reasoning models suffer from predictable, catastrophic failure modes:

* 🚨 **Selector Hallucination:** Models infer DOM selectors from guesswork, creating brittle classes, arbitrary indices, or fabricated attributes that fail under dynamic client hydration or CI headless runs.
* 🎭 **Test Greenwashing:** Agents generate tautological assertions (`expect(true).toBe(true)`, mocking away critical network boundaries, or swallowing uncaught exceptions) just to satisfy prompt completion with an artificial green checkmark.
* 🌀 **Context Starvation:** Without architectural grounding, agents generate tests in isolation—blind to existing fixtures, authentication states, seed data, and testing conventions.
* 🩹 **Flakiness by Design:** Models default to antipatterns—hardcoded timeouts (`waitForTimeout`), missing auto-wait conditions, and unisolated state leakage that turn suites into flaky nightmares.

**Reasoning alone is not enough.** A model cannot reason about a DOM state it cannot probe, nor can it uphold testing standards it was never given.

**M.A.T.E.** bridges this gap. By uniting **Context Engineering** (spec-driven test cases, domain boundaries, and fixture architecture) with **Harness Engineering** (deterministic live execution via `@playwright/cli` and accessibility-first locator verification), M.A.T.E. transforms generic reasoning models and coding agents into deterministic, production-grade Software Development Engineers in Test (SDETs).

---

## ⚡ Quick Start

Bootstrap M.A.T.E. in any TypeScript or JavaScript Playwright project with a single command:

```bash
# Using npx (zero installation required)
npx mate-sdt install

# Or install as a development dependency
npm install --save-dev mate-sdt
npx mate-sdt install
```

The interactive installer:
1. Detects your project structure, package manager (`npm`, `pnpm`, `yarn`, `bun`), and testing setup.
2. Injects M.A.T.E.'s agent instructions (`.agents/skills/`, `.cursorrules`, `CLAUDE.md`, or Antigravity configurations).
3. Configures Context Engineering files (`docs/test-cases/`, design documents, and testing manifests).
4. Sets up the execution harness (`@playwright/cli` live interaction and deterministic test generators).

---

## 🏛 Core Pillars

```
                   ┌──────────────────────────────────────────────┐
                   │               M.A.T.E. Engine                │
                   └──────────────────────┬───────────────────────┘
                                          │
         ┌───────────────────┬────────────┴───────┬───────────────────┐
         ▼                   ▼                    ▼                   ▼
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│     Context     │ │     Harness     │ │   Continuous    │ │   SDET-Grade    │
│   Engineering   │ │   Engineering   │ │  Verification   │ │  Craftsmanship  │
├─────────────────┤ ├─────────────────┤ ├─────────────────┤ ├─────────────────┤
│ • App Domain    │ │ • Live Browser  │ │ • Zero False    │ │ • Page Objects  │
│ • State & Fixt. │ │ • @playwright/  │ │   Positives     │ │ • Clean Fixt.   │
│ • docs/test-    │ │   cli tooling   │ │ • Anti-Mocking  │ │ • Atomic Runs   │
│   cases/ specs  │ │ • Selector gen  │ │   sanity checks │ │ • CI Readiness  │
└─────────────────┘ └─────────────────┘ └─────────────────┘ └─────────────────┘
```

### 1. Context Engineering
AI agents cannot test what they do not comprehend. M.A.T.E. structures application domain models, user flows, authenticated states, and requirements into high-density context assets under `docs/test-cases/` and system prompts, grounding the agent before a single line of test code is drafted.

### 2. Harness Engineering & Deterministic Tooling
Say goodbye to selector hallucination. M.A.T.E. integrates runtime harnesses (such as `@playwright/cli`) that allow the AI agent to interact with live running applications, inspect real DOM trees, probe accessibility snapshots, and generate resilient, accessibility-first locators (`getByRole`, `getByLabel`, `getByTestId`).

### 3. Continuous Verification & Anti-Greenwashing
Passing tests mean nothing if they aren't testing real behavior. M.A.T.E. enforces negative verification, fault-injection checks, and intentional mutation to guarantee tests fail when functionality breaks and pass strictly when business requirements are satisfied.

### 4. SDET-Grade Craftsmanship
Tests must be maintainable by human engineers. M.A.T.E. enforces strict architectural patterns: Page Object Model (POM) or App Actions, custom composable fixtures, zero arbitrary wait times (`waitForTimeout` is banned), and clean reporting.

---

## 🛠 The 16 Skills Ecosystem

M.A.T.E. modularizes the entire Quality Engineering lifecycle into 16 composable agent skills:

| Skill | Focus | What it does |
|---|---|---|
| 📐 `test-case-design` | Strategy & Planning | Derives boundary values, equivalence partitions, and edge cases from user stories into `docs/test-cases/`. |
| 🎭 `playwright-test-generator` | Authoring | Crafts production-grade Playwright tests adhering strictly to project conventions and atomic patterns. |
| 🔍 `dom-locator-strategy` | Locators & Selectors | Audits accessibility trees and enforces resilient locators, banning fragile CSS/XPath paths. |
| 🧪 `anti-greenwashing-audit` | Quality Gate | Scans test suites for dummy assertions, swallowed exceptions, and tautological checks. |
| ⚡ `flakiness-eliminator` | Reliability | Diagnoses race conditions, hydration delays, and auto-waiting issues; replaces arbitrary timeouts. |
| 🧩 `fixture-architecture` | Infrastructure | Builds typed, composable Playwright fixtures (auth states, clean databases, mock servers). |
| 📑 `page-object-modeling` | Architecture | Generates and refactors scalable Page Object Models (POM) with single-responsibility principles. |
| 🌐 `api-test-integration` | Full-Stack QA | Unifies API contracts, backend seed states, and UI flows into seamless end-to-end scenarios. |
| 🛡 `contract-testing` | Integrations | Validates schema definitions (OpenAPI/Swagger) against live payloads. |
| 📊 `test-reporting-analytics` | Visibility | Enriches Allure, HTML, and JUnit reports with meaningful telemetry, steps, and attachments. |
| ⏱ `performance-smoke-k6` | Non-Functional | Bridges functional workflows into load scenarios with k6 and Playwright metrics. |
| ♿ `accessibility-axe-core` | Compliance | Embeds automated WCAG 2.1/2.2 AA audits via `@axe-core/playwright`. |
| 🐳 `ci-cd-pipeline-tuning` | DevOps | Optimizes GitHub Actions, GitLab CI, sharding, parallel workers, and artifact caching. |
| 🧬 `mutation-testing-gate` | Rigor | Verifies test efficacy by injecting subtle mutations into application source code. |
| 🔄 `visual-regression-testing` | UX & Visual | Configures pixel-perfect visual comparisons with dynamic masking and cross-browser stability. |
| 📚 `documentation-as-code` | Governance | Keeps testing matrices, architecture decision records (ADRs), and runbooks synchronized. |

---

## 📦 Ecosystem Repositories

* [**`mate-sdt/mate-sdt`**](https://github.com/mate-sdt/mate-sdt): The core framework, CLI installer (`npx mate-sdt install`), skill manifests, and runtime harness definitions.
* [**`mate-sdt-starter-playwright`**](https://github.com/mate-sdt): *(Reference Template)* Zero-config TypeScript Playwright template preconfigured with M.A.T.E. skills, sample POM, and CI workflows.
* [**`mate-sdt/manifesto`**](https://github.com/mate-sdt/mate-sdt/blob/main/MANIFESTO.md): The philosophical and technical principles guiding modern AI-augmented test engineering.

---

## 🤝 Community & Contributing

M.A.T.E. is proudly open-source and community-driven. Whether you are an SDET looking to supercharge your team's velocity, an open-source maintainer, or an AI developer building agent tooling:

* 📖 Read our [Contributing Guide](https://github.com/mate-sdt/mate-sdt/blob/main/CONTRIBUTING.md).
* 💬 Join discussions, report issues, or propose new skills via [GitHub Issues](https://github.com/mate-sdt/mate-sdt/issues).
* ⭐ Star the [primary repository](https://github.com/mate-sdt/mate-sdt) to support the project.

---

<div align="center">
<sub>Built with 🧉 for the future of software quality. Sponsored by <a href="https://github.com/tonycrespo">Tony Crespo</a> & the <a href="https://github.com/mate-sdt">M.A.T.E. Team</a>.</sub>
</div>
