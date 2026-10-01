## Phase 0: Setup

### What I learned
- Monorepo layout: backend and frontend in one repo, one shared history.
- Git hygiene: .gitignore excludes generated output (target/, node_modules/)
  and secrets (.env); .env.example documents variables without leaking them.
- Why leaked secrets are permanent in Git history, and that rotation is the
  only real fix.
- Docker Compose: one YAML to define and run local infra reproducibly.
- Named volumes: the container is disposable, the volume is the memory.

### Key decisions
- Pinned postgres:16 (not :latest) for reproducible builds.
- Secrets via ${POSTGRES_PASSWORD} from .env, never hardcoded.