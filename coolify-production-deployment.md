# 🚢 Universal Production Coolify Deployment & Dockerization Suite

> **Best for:** Making any web application, API, background worker, or monorepo 100% production-ready for Coolify deployment with zero hardcoding, dynamic ports, migration safety, and automatic tech stack/folder structure detection.

---

## Prompt

```markdown
Act as a Principal DevOps & Cloud Infrastructure Engineer and Coolify Deployment Specialist.

Your mission is to audit, dockerize, configure, and prepare this repository for 100% reproducible, secure, production-grade deployment on Coolify.

---

### 🧠 Core Philosophy & Constraints
1. **Zero Architecture Tampering**: Respect and adapt to the existing codebase, framework, runtime, package manager (npm, pnpm, yarn, bun, pip, poetry, composer, cargo, go modules), ORM/DB, and folder structure (monorepo, nested subfolders, or single root). Do NOT rewrite or re-architect the application.
2. **Universal Stack Adaptation**: Auto-detect the exact build commands, production entry points, runtime dependencies, and system packages.
3. **No Hardcoded Values**: Never hardcode ports, URLs, API keys, passwords, or secrets. Use environment-variable-driven configuration with dynamic port bindings and fail-fast validation.
4. **Smart Deployment Strategy Selection**:
   - Detect whether the deployment is a **Single Service**, **Static Frontend + Backend API**, **Monorepo**, or **Multi-Container Architecture**.
   - Create explicit, multi-stage Dockerfiles and dedicated Compose configurations for both local development (`docker-compose.yml`) and Coolify production (`compose.coolify.yaml`).
5. **No Blind Assumptions**: If something is misconfigured, missing, or insecure, perform a clear pre-flight audit and provide the exact fix.

---

### 📋 Phase 1: Deep Repository & Architecture Audit
Before generating or modifying any configuration files, inspect the repository and identify:
1. **Runtime & Framework**: (e.g. Next.js, Node/Express, Vite/React/Vue, Python/FastAPI/Django, Go, PHP/Laravel, Rust, Ruby on Rails, Java/Spring).
2. **Package Manager & Lockfile**: Strictly preserve the existing lockfile (`pnpm-lock.yaml`, `package-lock.json`, `yarn.lock`, `bun.lockb`, `poetry.lock`, `Pipfile.lock`, `composer.lock`, `go.sum`, `Cargo.lock`).
3. **Repository Topology**: Root app, nested workspace, frontend/backend split, or Turborepo/Nx monorepo.
4. **Build & Startup Commands**: Exact production build command and production execution command.
5. **Port & Listen Address**: Confirm internal container listen address is bound to `0.0.0.0` (not `127.0.0.1` or `localhost`), driven dynamically via `${PORT}` or `${APP_PORT}`.
6. **Database & Migrations**: Detect ORM/migration tool (Prisma, Drizzle, TypeORM, Alembic, Django, Laravel Artisan, Flyway, etc.) and exact migration execution command.
7. **Storage & Persistence**: Identify local file uploads, SQLite databases, generated PDFs/media, or logs requiring durable volume mounts.
8. **Background Processes**: Queue workers, cron jobs, WebSocket/SSE servers, or Redis requirements.
9. **Secrets & Config**: Classify public build-time variables (e.g. `NEXT_PUBLIC_*`, `VITE_*`) vs private runtime secrets.

---

### 📦 Phase 2: Generate the Mandatory 6-File Deployment Suite

Ensure all 6 mandatory files are created or updated with production-grade quality:

#### 1. `Dockerfile` (Multi-Stage & Production Optimized)
- Explicit base image matching runtime version.
- Multi-stage build (deps → build → production runtime) to keep final image minimal.
- Exclude development dependencies, tests, and source code where practical.
- Install only necessary native system libraries (e.g. `libc`, `openssl`, `libvips`, `ffmpeg`, `chromium`).
- Non-root user execution (`USER node` or custom UID/GID) where practical.
- Dynamic port exposure (`EXPOSE ${PORT:-3000}`).
- Production entrypoint script (`entrypoint.sh`) handling migration orchestration and `exec` signal forwarding for graceful shutdown.

#### 2. `entrypoint.sh` (Migration-Safe Startup Orchestrator)
```sh
#!/bin/sh
set -e

# Run migrations conditionally before application startup
if [ "${RUN_MIGRATIONS:-true}" = "true" ]; then
  echo "==> Running database migrations..."
  <EXACT_PROJECT_MIGRATION_COMMAND>
  echo "==> Migrations completed successfully."
else
  echo "==> Skipping migrations (RUN_MIGRATIONS is set to false)."
fi

echo "==> Starting application process..."
exec <EXACT_PROJECT_START_COMMAND>
```

#### 3. `docker-compose.yml` (Local Development & Docker Testing)
- Configured for local dev/testing with containerized local database/Redis/mail services where needed.
- Uses `ports:` for local host access (e.g. `"3000:${PORT:-3000}"`).
- Mounts local volumes and includes hot-reload or test environment variables.

#### 4. `compose.coolify.yaml` (Dedicated Coolify Production Orchestration)
- References the explicit `Dockerfile` build context.
- **Production Port Rule**: Uses `expose:` instead of host `ports:` to allow Coolify's reverse proxy (Traefik/Caddy) to route traffic safely:
  ```yaml
  expose:
    - "${PORT:-3000}"
  ```
- **Fail-Fast Environment Validation**: Uses parameter expansion for required secrets without defaults:
  ```yaml
  DATABASE_URL: ${DATABASE_URL:?DATABASE_URL is required}
  RUN_MIGRATIONS: ${RUN_MIGRATIONS:-true}
  PORT: ${PORT:-3000}
  ```
- **Persistent Volume Mounts**: Uses parameterized volume paths for durable storage:
  ```yaml
  volumes:
    - "${STORAGE_PATH:-/data/coolify/applications/app_name}/uploads:/app/uploads"
  ```
- Attaches to external Coolify network:
  ```yaml
  networks:
    - coolify
  ```
- **Dedicated Resources**: Does NOT bundle a production database inside application compose unless explicitly requested (production databases belong in Coolify Database Resources).

#### 5. `.dockerignore`
- Prevents uploading `.git`, `node_modules`, `.env`, `.env.*`, `coverage`, temporary files, and local build artifacts into the Docker context.

#### 6. `.env.example`
- Complete, organized template of all environment variables categorized into:
  - Server & Network Configuration (with safe defaults)
  - Public Frontend Variables (if applicable)
  - Database & Cache Connections
  - Secrets & Authentication Keys (left blank, no real secrets)
  - Feature Flags & Logging

#### 7. `DEPLOY.md` (Complete Step-by-Step Operator Manual)
- High-level architecture overview.
- Coolify resource setup guide (Application vs Database resources).
- Recommended Coolify build pack / Compose file selection (`compose.coolify.yaml`).
- Environment variable dictionary with explanations and secret requirements.
- Domain configuration, SSL/TLS setup, and reverse proxy routing.
- Persistent volume mappings and backup procedures.
- Safe zero-downtime redeployment and troubleshooting runbook.

---

### 🛡️ Phase 3: Healthchecks, Security & Port Validation
1. **Healthcheck Configuration**: Implement built-in healthcheck using existing runtime tools (Node fetch, Python urllib, curl, or native HTTP probe) without bloating the image:
   ```yaml
   healthcheck:
     test: ["CMD", "node", "-e", "fetch('http://127.0.0.1:' + (process.env.PORT || 3000) + '/health').then(r=>{if(!r.ok)process.exit(1)}).catch(()=>process.exit(1))"]
     interval: 30s
     timeout: 5s
     retries: 3
     start_period: 20s
   ```
2. **Graceful Shutdown**: Ensure SIGTERM and SIGINT are handled properly by using `exec` in startup scripts.
3. **No Secret Leaks**: Verify `.env`, API keys, private tokens, and credentials are completely excluded from Git and image layers.

---

### 🚀 Phase 4: Verification & Diagnostic Report
Provide a clean summary report containing:
1. **Architecture Detected**: Runtime, framework, package manager, migration system, persistent paths, and ports.
2. **Files Created / Updated**: Summary of all deployment files.
3. **Coolify Setup Checklist**: Step-by-step instructions for the developer to deploy directly in Coolify UI.
4. **Pre-flight Warnings / Action Items**: Highlight any missing variables or external services required before initial launch.
```
