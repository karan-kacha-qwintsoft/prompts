# 🚀 Battle-Tested AI Prompt Library & Templates

A curated collection of production-grade, tested prompt templates designed to accelerate development, improve code quality, streamline debugging, and deliver visually stunning user interfaces with AI coding assistants.

---

## 📑 Table of Contents

1. [How to Use These Templates](#-how-to-use-these-templates)
2. [🏗️ Architecture & Feature Planning](#️-architecture--feature-planning)
   - [1. Feature Implementation Blueprint](#1-feature-implementation-blueprint)
   - [2. System Architecture & Tech Stack Evaluator](#2-system-architecture--tech-stack-evaluator)
3. [🎨 Modern Frontend & UI/UX Engineering](#-modern-frontend--uiux-engineering)
   - [3. Premium Modern Component / Page Generator](#3-premium-modern-component--page-generator)
   - [4. Responsive & Micro-Interaction Polish](#4-responsive--micro-interaction-polish)
4. [⚙️ Backend, APIs & Database Design](#️-backend-apis--database-design)
   - [5. Robust REST / GraphQL API Builder](#5-robust-rest--graphql-api-builder)
   - [6. Database Schema & Migration Strategy](#6-database-schema--migration-strategy)
5. [🚢 DevOps, Docker & Coolify Deployment](#-devops-docker--coolify-deployment)
   - [7. Production-Ready Coolify & Docker Deployment](#7-production-ready-coolify--docker-deployment)
6. [🔍 Debugging & Root Cause Analysis (RCA)](#-debugging--root-cause-analysis-rca)
   - [8. Deep Root-Cause Bug Hunter](#8-deep-root-cause-bug-hunter)
   - [9. Performance & Bottleneck Optimizer](#9-performance--bottleneck-optimizer)
7. [🛡️ Code Review, Security & Refactoring](#️-code-review-security--refactoring)
   - [10. Senior Engineer Code Review & Security Audit](#10-senior-engineer-code-review--security-audit)
   - [11. Clean Architecture & Modular Refactor](#11-clean-architecture--modular-refactor)
8. [🧪 Testing & Quality Assurance](#-testing--quality-assurance)
   - [12. Full-Coverage Test Suite Generator](#12-full-coverage-test-suite-generator)
9. [📝 Documentation & Developer Experience](#-documentation--developer-experience)
   - [13. Production README & API Documentation](#13-production-readme--api-documentation)
10. [💳 Payments & Legal Compliance](#-payments--legal-compliance)
   - [14. Razorpay Website Verification & Mandatory Legal Suite](#14-razorpay-website-verification--mandatory-legal-suite)

---

## 💡 How to Use These Templates

1. Copy the prompt block.
2. Replace all `[PLACEHOLDERS]` (e.g. `[FRAMEWORK]`, `[FEATURE_NAME]`, `[CODE]`) with your project details.
3. Feed it to your AI coding assistant (Antigravity, Claude, ChatGPT, etc.).
4. Review the generated plan/code before executing or deploying.

---

## 🏗️ Architecture & Feature Planning

### 1. Feature Implementation Blueprint
> **Best for:** Complex features where you want the AI to plan edge cases and architecture before touching any code.

```markdown
Act as a Principal Software Engineer. I need to implement a new feature: "[FEATURE_NAME]".

### Project Context:
- Framework & Runtime: [e.g., Next.js 14 App Router, Node.js, Express, Go]
- Database & ORM: [e.g., PostgreSQL with Drizzle ORM / Prisma]
- State Management / Styling: [e.g., Zustand, Tailwind CSS, Vanilla CSS]

### Requirements:
[List key functional and non-functional requirements here]

### Instructions:
1. Do NOT write code yet. First, provide a structured implementation blueprint:
   - Architecture overview & data flow.
   - Database schema changes (tables, indexes, relations) if needed.
   - API contract (endpoints, request/response DTOs, error schemas).
   - Component / Service hierarchy.
   - Edge cases, error handling, and security considerations.
2. Provide a phased, step-by-step checklist we will execute together.
3. Wait for my confirmation on the plan before generating the code.
```

---

### 2. System Architecture & Tech Stack Evaluator
> **Best for:** Choosing tools, libraries, or designing a clean high-scale architecture from scratch.

```markdown
Act as a Solutions Architect. I am designing a system for: "[SYSTEM_NAME_OR_PURPOSE]".

### Scale & Goals:
- Target Users / Throughput: [e.g., 50k DAU, real-time sync, high read/write ratio]
- Core Constraints: [e.g., Self-hosted on Coolify / VPS, low latency, tight budget]
- Key Integrations: [e.g., Stripe, S3-compatible storage, WebSockets]

### Please Provide:
1. Recommended Architecture Pattern (Monolith vs Modular Monolith vs Microservices).
2. Recommended Tech Stack with clear trade-offs (Pros, Cons, Operational Complexity).
3. Data Model & Cache Strategy (Database choice, Redis caching, indexing).
4. Potential Failure Modes & Mitigation Strategies.
5. High-level ASCII or Mermaid sequence diagram of the primary workflow.
```

---

## 🎨 Modern Frontend & UI/UX Engineering

### 3. Premium Modern Component / Page Generator
> **Best for:** Creating modern, WOW-factor interfaces with glassmorphism, gradients, micro-animations, and modern typography instead of basic, generic MVP designs.

```markdown
Act as an Elite UI/UX Designer and Lead Frontend Engineer. Build a stunning, modern "[COMPONENT_OR_PAGE_NAME]".

### Technical Specs:
- Framework: [e.g., React / Next.js / Vue / Vanilla HTML+JS]
- Styling: [e.g., Modern Vanilla CSS / Tailwind CSS]
- Theme: [Dark Mode / Sleek Glassmorphism / Minimalist Luxury]

### Design Rules:
1. **Visual Excellence**: Avoid basic colors (pure red, green, blue). Use tailored HSL palettes, subtle gradients, and dark accents.
2. **Typography**: Use modern typography (e.g., Inter, Outfit, Plus Jakarta Sans) with proper hierarchy and letter-spacing.
3. **Micro-interactions**: Include fluid hover effects, smooth transitions, focus states, and interactive feedback.
4. **Depth & Texture**: Use subtle borders (`rgba(255,255,255,0.08)`), backdrop filters (`blur`), and multi-layered soft drop shadows.
5. **Responsiveness**: Fully responsive across mobile (<640px), tablet (<1024px), and desktop.
6. **No Placeholders**: Write realistic, high-converting copy and complete layouts without leaving TODOs.

Please output the complete, production-ready code.
```

---

### 4. Responsive & Micro-Interaction Polish
> **Best for:** Taking an existing plain component and elevating it to a high-end, dynamic experience.

```markdown
Review the following UI code. It looks too generic and basic. Transform it into a modern, delightful interface.

```[LANG]
[PASTE EXISTING CODE]
```

### Improvements Required:
1. Elevate the visual aesthetics (sleek color palette, refined padding/margins, modern card designs).
2. Add smooth micro-animations (hover lift, button glow, shimmer loading states, smooth accordion transitions).
3. Ensure strict responsive design for all screen widths.
4. Enhance accessibility (ARIA labels, keyboard focus rings, semantic HTML).
5. Retain all existing functionality and state bindings.
```

---

## ⚙️ Backend, APIs & Database Design

### 5. Robust REST / GraphQL API Builder
> **Best for:** Generating production-ready endpoints with validation, auth, and error handling.

```markdown
Act as a Senior Backend Engineer. Build the API implementation for: "[FEATURE_OR_ENDPOINT]".

### Tech Stack:
- Runtime & Framework: [e.g., Node.js / Express / NestJS / FastAPI / Go]
- Database / ORM: [e.g., PostgreSQL, Prisma / Drizzle]
- Validation: [e.g., Zod, class-validator, Pydantic]

### Endpoint Details:
- Method & Path: [e.g., POST /api/v1/projects/:id/members]
- Authentication / Authorization: [e.g., JWT Bearer token, Role: Admin or Owner]
- Payload: [Define expected fields]

### Requirements:
1. Strict input validation with clear, sanitized error messages.
2. Database query with proper transactions if multiple updates occur.
3. Defensive error handling (400 for bad input, 401/403 for auth, 404 for missing resource, 409 for conflicts, 500 for unhandled exceptions).
4. Structured logging (avoid leaking passwords, tokens, or PII).
5. Clean separation of concerns (Route -> Controller/Handler -> Service/Repository).
```

---

### 6. Database Schema & Migration Strategy
> **Best for:** Clean schema design, indexing, foreign keys, and safe zero-downtime migrations.

```markdown
Act as a Database Architect. I need to design the schema for: "[DATA_DOMAIN]".

### Requirements:
- Engine: [PostgreSQL 16 / MySQL 8 / SQLite]
- ORM/Migration Tool: [Drizzle / Prisma / Flyway / raw SQL]
- Entities & Relationships: [Describe the entities and how they relate]

### Deliverables:
1. Normalized relational schema with appropriate data types (UUIDs/ULIDs, timestamps, enums).
2. Indexing strategy (single, composite, partial, or unique indexes) explained with query patterns.
3. Migration script with rollback safeguards.
4. Foreign key constraints and cascade rules (CASCADE vs SET NULL vs RESTRICT).
5. Performance notes (partitioning, JSONB usage, concurrency locking).
```

---

## 🚢 DevOps, Docker & Coolify Deployment

### 7. Production-Ready Coolify & Docker Deployment
> **Best for:** Preparing or auditing any repository for production deployment on Coolify using explicit Dockerfiles and Compose configurations.

```markdown
Act as a DevOps & Coolify Specialist. Prepare this project for reliable, production-ready deployment on Coolify.

### Repository Context:
- Language/Framework: [e.g., Node.js Next.js / Python FastAPI / Go]
- Package Manager: [e.g., pnpm / npm / bun / pip]
- Database: [e.g., Dedicated Coolify PostgreSQL resource]
- Migrations: [e.g., Drizzle / Prisma / Alembic]
- Port: [e.g., 3000]

### Mandatory Deliverables:
1. **Dockerfile**:
   - Multi-stage build (build stage vs minimal production runtime).
   - Use the exact existing package manager and respect lockfiles.
   - Non-root user where practical.
   - Handle Unix signals properly with `exec`.
2. **docker-compose.yml**:
   - For local development & testing (includes local DB/Redis if needed).
3. **compose.coolify.yaml**:
   - For production Coolify deployment.
   - Use `expose:` (never bind public host ports directly; Coolify reverse proxy handles ingress).
   - External Coolify network configuration.
   - Environment variables using `${VAR:-default}` or `${VAR:?required}` syntax.
4. **entrypoint.sh** (if migrations exist):
   - Controlled via `RUN_MIGRATIONS=${RUN_MIGRATIONS:-true}`.
   - Run migrations before starting the app; exit non-zero if migrations fail.
5. **.dockerignore**:
   - Comprehensive exclusions (.git, node_modules, .env*, local logs).
6. **.env.example**:
   - All environment variables with safe defaults or empty secret placeholders.
7. **DEPLOY.md**:
   - Step-by-step instructions for configuring the resource in Coolify.
```

---

## 🔍 Debugging & Root Cause Analysis (RCA)

### 8. Deep Root-Cause Bug Hunter
> **Best for:** Intermittent bugs, race conditions, cryptic crashes, or unexpected runtime behavior.

```markdown
Act as an Expert Systems Debugger. I am encountering an issue and need a systematic Root Cause Analysis (RCA).

### Symptoms & Error Details:
- Error Message / Stack Trace:
```text
[PASTE STACK TRACE OR LOGS]
```
- Expected Behavior: [What should happen]
- Actual Behavior: [What actually happens]
- Environment: [OS, Node/Python/Go version, browser, database]

### Relevant Code:
```[LANG]
[PASTE RELEVANT CODE SNIPPET]
```

### Instructions:
1. **Analyze**: Formulate 3 distinct hypotheses for what causes this issue.
2. **Validate**: Explain how to verify each hypothesis (diagnostic logs, breakpoints, or edge cases).
3. **Root Cause**: Identify the most probable root cause with technical justification.
4. **Fix**: Provide the minimal, surgical code fix that solves the problem without breaking existing logic.
5. **Regression Prevention**: Suggest a test case or guardrail to prevent this from ever happening again.
```

---

### 9. Performance & Bottleneck Optimizer
> **Best for:** Slow API responses, high CPU/memory usage, or heavy frontend bundle sizes.

```markdown
Act as a Performance Engineering Specialist. Analyze and optimize the following code/query:

```[LANG]
[PASTE CODE OR SQL QUERY]
```

### Metrics & Current Problem:
- Current performance: [e.g., 850ms latency, N+1 queries, 2MB bundle size, memory spike]
- Target goal: [e.g., <50ms response, sub-100KB initial bundle, stable memory]

### Deliverables:
1. Identification of all performance bottlenecks (time complexity, unnecessary re-renders, unindexed queries, blocking I/O).
2. Refactored code with benchmark comparisons (before vs after).
3. Recommended caching, pagination, or streaming strategy.
```

---

## 🛡️ Code Review, Security & Refactoring

### 10. Senior Engineer Code Review & Security Audit
> **Best for:** Auditing PRs, new features, or legacy code before merging to main/production.

```markdown
Act as a Principal Engineer and Application Security Auditor. Review the following code:

```[LANG]
[PASTE CODE]
```

### Audit Criteria:
1. **Security Vulnerabilities**:
   - Injection risks (SQLi, XSS, Command Injection).
   - Auth flaws, privilege escalation, or IDOR.
   - Sensitive data exposure in logs, errors, or client bundles.
   - CSRF, CORS, and rate limiting gaps.
2. **Code Quality & Architecture**:
   - Adherence to SOLID principles and Clean Architecture.
   - Error handling & edge case coverage.
   - Memory management & resource leaks (unclosed sockets/streams/handles).
3. **Actionable Recommendations**:
   - Categorize issues as: 🚨 Critical, ⚠️ Warning, or 💡 Enhancement.
   - Provide concrete refactored diffs for all critical and warning findings.
```

---

### 11. Clean Architecture & Modular Refactor
> **Best for:** Untangling spaghetti code, breaking down god-files, and improving testability.

```markdown
The following file has grown too large and violates the Single Responsibility Principle. Help me refactor it cleanly:

```[LANG]
[PASTE CODE]
```

### Refactoring Guidelines:
1. Decompose into focused, single-purpose modules/functions.
2. Decouple business logic from framework-specific presentation and database layers.
3. Use dependency injection or composition to make units easily testable.
4. Preserve 100% of existing behavior and external interfaces.
5. Show the new file directory structure and the exact code for each new module.
```

---

## 🧪 Testing & Quality Assurance

### 12. Full-Coverage Test Suite Generator
> **Best for:** Creating bulletproof unit, integration, and edge-case tests.

```markdown
Act as a QA Architect. Generate a complete test suite for the following component/function:

### Target Code:
```[LANG]
[PASTE CODE]
```

### Testing Framework:
- Framework: [e.g., Vitest / Jest / PyTest / Go testing]
- Mocking Library: [e.g., MSW, vi.mock, unittest.mock]

### Requirements:
1. **Happy Path Tests**: Normal expected inputs and responses.
2. **Edge Cases**: Null, undefined, empty collections, extreme boundary numbers, unicode strings.
3. **Error Cases**: Network timeouts, database failures, unauthenticated requests, invalid payload schemas.
4. **State / Lifecycle**: Race conditions, asynchronous timing, idempotency.
5. Clean arrangement using Arrange-Act-Assert (AAA) pattern with descriptive test names (`it('should ... when ...')`).
```

---

## 📝 Documentation & Developer Experience

### 13. Production README & API Documentation
> **Best for:** Creating beautiful open-source or internal project documentation that devs love.

```markdown
Act as a Technical Writer and Developer Advocate. Generate a comprehensive, professional `README.md` for: "[PROJECT_NAME]".

### Project Summary:
- What it does: [Brief summary]
- Target Audience: [Developers / End Users / DevOps]
- Tech Stack: [Languages, frameworks, databases, cloud tools]
- Key Features: [Bullet list of 4-6 main features]

### Structure to Include:
1. Project title with badge shields (build status, license, version).
2. Clean value proposition & high-level architecture overview.
3. Prerequisites & Environment Variables table.
4. Quick Start guide (step-by-step local setup with commands).
5. Available scripts (`npm run dev`, `test`, `build`, etc.).
6. Deployment instructions & Docker setup.
7. Contributing guidelines & License.
```

---

## 💳 Payments & Legal Compliance

### 14. Razorpay Website Verification & Mandatory Legal Suite
> **Best for:** Preparing an existing production website for Razorpay payment activation and website verification by implementing compliant, customer-facing legal and business pages.

````markdown
Act as a Lead Full-Stack Engineer & Compliance Specialist. Prepare this website for Razorpay payment activation and website verification by implementing all required customer-facing legal and business information pages.

### Phase 1: Repository & Architecture Audit (Do this first)
Before altering any code:
1. Identify the framework, routing system, styling, layout components (Header, Footer), typography, and theme.
2. Check existing business/contact info across components, configuration, and environment files.
3. Inspect existing payment, checkout, pricing, order, shipping, and refund flows.
4. **Preserve Integrity**: Do NOT duplicate existing pages/components. Do NOT remove or break existing functionality, auth, cart, or payment logic. Preserve visual design and branding.

---

### Phase 2: Create/Update the 5 Required Public Pages
Implement these 5 publicly accessible pages (no login, payment, or permissions required):

#### A. Contact Us (`/contact`)
- Business / Company legal or brand name.
- Registered business address.
- Customer support email and phone number.
- Customer support operating hours / availability.
- (Optional) Working contact form if supported by the project.

#### B. Privacy Policy (`/privacy-policy`)
- Information collected (personal, contact, device, cookies, order info).
- Payment processing: Clearly state payments are securely processed via Razorpay. **Crucial**: Do NOT claim the website stores card/UPI/banking credentials if processed externally.
- Third-party service providers, data retention, security safeguards, user rights (access/deletion), and children's privacy.
- Contact details for privacy concerns & a visible "Last Updated" date.

#### C. Terms & Conditions (`/terms-and-conditions`)
- Acceptance of terms, user eligibility, account responsibilities.
- Product/service descriptions, transparent pricing, applicable taxes.
- Payment processing, order confirmation, and delivery/fulfillment terms.
- Intellectual property, prohibited activities, limitation of liability, disclaimers, suspension/termination, governing law & jurisdiction.

#### D. Refund & Cancellation Policy (`/refund-cancellation`)
- Cancellation eligibility, request window, and submission steps.
- Refund eligibility, non-refundable items/services, and processing timelines (e.g., 5-7 business days for gateway credit).
- Policy for failed, duplicate, or incorrect payments.
- Support contact channel for refund disputes.
- **Match Business Model**: Accurately reflect physical returns or digital service cancellation rules. Do not make unsupported promises.

#### E. Shipping & Delivery Policy (`/shipping-delivery`)
- **For Physical Goods**: Delivery zones, shipping charges, estimated processing/delivery timelines, courier partners, tracking, damaged package protocols.
- **For Digital Goods / Services**: Clearly state digital delivery mechanism (instant account access, email delivery, download link), fulfillment turnaround, and resolution steps if access fails.
- **Rule**: DO NOT add physical shipping terms to a digital-only service.

---

### Phase 3: Footer Integration
- Integrate all 5 links prominently into the **existing footer** (do not create a secondary footer):
  `Contact Us` (`/contact`), `Privacy Policy` (`/privacy-policy`), `Terms & Conditions` (`/terms-and-conditions`), `Refund / Cancellation Policy` (`/refund-cancellation`), `Shipping / Delivery Policy` (`/shipping-delivery`).
- Must be accessible across all pages, working seamlessly on mobile and desktop without requiring authentication.

---

### Phase 4: Business Data Integrity & Design
1. **Real Data Only**: Extract business name, address, email, and phone from existing project config/env. Never fabricate addresses, phones, or GSTNs. If missing, create clear placeholder variables in config.
2. **Consistent Design**: Reuse existing layout, header, footer, colors, font hierarchy, and card/button styles.
3. **Readable Layout**: Use a readable max-width, clean typography, clear section spacing, and a "Last Updated" timestamp.
4. **SEO Metadata**: Provide accurate page titles (e.g., `Terms & Conditions | [Business Name]`), meta descriptions, and canonical tags.

---

### Phase 5: Verification & Audit Report
1. Verify responsiveness across desktop, tablet, and mobile (no horizontal scroll).
2. Ensure zero console errors, hydration mismatches, broken routes, or TypeScript/lint issues.
3. Provide a final summary report containing:
   - Existing pages found vs created/updated.
   - Exact routes and footer integration status.
   - Source of business information used & any missing fields needed from the user.
   - Verification checklist results.
````

---

## 💡 Quick Tips for Prompting Coding AIs

- **Give Context First**: Specify language, runtime version, ORM, and styling system before asking for code.
- **Enforce Constraints**: Tell the AI what *not* to do (e.g., "Do not install new dependencies", "Do not rewrite existing DB logic").
- **Phase Execution**: For large tasks, ask the AI to first output a plan and wait for your confirmation before writing code.
- **Request Diffs for Edits**: When updating existing large files, ask the AI for unified diffs or targeted changes to avoid truncation.
