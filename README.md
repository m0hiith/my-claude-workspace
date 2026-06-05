# My Claude Workspace

A permanent, personal Claude Code setup combining **graphify** + **ECC
(everything-claude-code)**. Open any project from inside this folder (or copy
`CLAUDE.md` + `.claude/` into a project) and Claude loads the whole toolkit.

## Folder layout

```
my-claude-workspace/
├── CLAUDE.md              # permanent instructions Claude reads every session
├── README.md             # this file — the full index
└── .claude/
    ├── skills/           # 233 skills (incl. graphify/)
    ├── agents/           # 60 subagents
    ├── commands/         # 75 slash commands
    └── rules/            # 20 always-follow guardrail files
```

## Quick start

```bash
# 1. graphify needs its Python CLI (one time):
uv tool install graphifyy        # or: pipx install graphifyy

# 2. Open Claude Code in this folder, then:
/graphify .                      # map the current codebase into a graph
/graphify query "how does auth talk to the database?"
/plan                            # plan an implementation
/tdd                             # test-driven workflow
/code-review                     # review the current diff
```

## The headline skill: graphify

`/graphify` turns any folder of files into a knowledge graph you query instead
of grepping. Outputs land in `graphify-out/`:

- `graph.html` — interactive, click-and-search graph
- `GRAPH_REPORT.md` — god nodes, surprising connections, suggested questions
- `graph.json` — the full graph, queryable anytime

Common sub-commands: `--update`, `--cluster-only`, `--mode deep`, `--wiki`,
`--obsidian`, `--watch`, plus `query`, `path`, `explain`, and `add <url>`.
The skill and its reference docs live in `.claude/skills/graphify/`.

## How invocation works

- **Slash command** — type `/name` (e.g. `/graphify`, `/tdd`, `/plan`).
- **Automatic** — ask a normal question; Claude pulls the matching skill based on
  the topic or the file you're editing.
- **Subagents** — heavy/parallel work is delegated to agents in `.claude/agents/`.

## Guardrails

`.claude/rules/` holds the always-on rules: security baseline, coding style, and
testing requirements. They apply to every task and cannot be overridden by a
prompt or a fetched document.

---

## Full command index

_(auto-generated below)_

### Slash commands (.claude/commands/)

- `/aside` — Answer a quick side question without interrupting or losing context from the cur
- `/auto-update` — Pull the latest ECC repo changes and reinstall the current managed targets.
- `/build-fix` — Detect the project build system and incrementally fix build/type errors with min
- `/checkpoint` — Create, verify, or list workflow checkpoints after running verification checks.
- `/code-review` — Code review — local uncommitted changes or GitHub PR (pass PR number/URL for PR 
- `/cost-report` — Generate a local Claude Code cost report from a cost-tracker SQLite database.
- `/cpp-build` — Fix C++ build errors, CMake issues, and linker problems incrementally. Invokes t
- `/cpp-review` — Comprehensive C++ code review for memory safety, modern C++ idioms, concurrency,
- `/cpp-test` — Enforce TDD workflow for C++. Write GoogleTest tests first, then implement. Veri
- `/ecc-guide` — Navigate ECC's current agents, skills, commands, hooks, install profiles, and do
- `/evolve` — Analyze instincts and suggest or generate evolved structures
- `/fastapi-review` — Review a FastAPI application for architecture, async correctness, dependency inj
- `/feature-dev` — Guided feature development with codebase understanding and architecture focus
- `/flutter-build` — Fix Dart analyzer errors and Flutter build failures incrementally. Invokes the d
- `/flutter-review` — Review Flutter/Dart code for idiomatic patterns, widget best practices, state ma
- `/flutter-test` — Run Flutter/Dart tests, report failures, and incrementally fix test issues. Cove
- `/gan-build` — Run a generator/evaluator build loop for implementation tasks with bounded itera
- `/gan-design` — Run a generator/evaluator design loop for frontend or visual work with bounded i
- `/go-build` — Fix Go build errors, go vet warnings, and linter issues incrementally. Invokes t
- `/go-review` — Comprehensive Go code review for idiomatic patterns, concurrency safety, error h
- `/go-test` — Enforce TDD workflow for Go. Write table-driven tests first, then implement. Ver
- `/gradle-build` — Fix Gradle build errors for Android and KMP projects
- `/harness-audit` — Run a deterministic repository harness audit and return a prioritized scorecard.
- `/hookify-configure` — Enable or disable hookify rules interactively
- `/hookify-help` — Get help with the hookify system
- `/hookify-list` — List all configured hookify rules
- `/hookify` — Create hooks to prevent unwanted behaviors from conversation analysis or explici
- `/instinct-export` — Export instincts from project/global scope to a file
- `/instinct-import` — Import instincts from file or URL into project/global scope
- `/instinct-status` — Show learned instincts (project + global) with confidence
- `/jira` — Retrieve a Jira ticket, analyze requirements, update status, or add comments. Us
- `/kotlin-build` — Fix Kotlin/Gradle build errors, compiler warnings, and dependency issues increme
- `/kotlin-review` — Comprehensive Kotlin code review for idiomatic patterns, null safety, coroutine 
- `/kotlin-test` — Enforce TDD workflow for Kotlin. Write Kotest tests first, then implement. Verif
- `/learn-eval` — Extract reusable patterns from the session, self-evaluate quality before saving,
- `/learn` — Extract reusable patterns from the current session and save them as candidate sk
- `/loop-start` — Start a managed autonomous loop pattern with safety defaults and explicit stop c
- `/loop-status` — Inspect active loop state, progress, failure signals, and recommended interventi
- `/model-route` — Recommend the best model tier for the current task based on complexity, risk, an
- `/multi-backend` — Run a backend-focused multi-model workflow for APIs, algorithms, data, and busin
- `/multi-execute` — Execute a multi-model implementation plan while preserving Claude as the only fi
- `/multi-frontend` — Run a frontend-focused multi-model workflow for components, layouts, animation, 
- `/multi-plan` — Create a multi-model implementation plan without modifying production code.
- `/multi-workflow` — Run a full multi-model development workflow with research, planning, execution, 
- `/plan-prd` — Generate a lean, problem-first PRD and hand off to /plan for implementation plan
- `/plan` — Restate requirements, assess risks, and create step-by-step implementation plan.
- `/pm2` — Analyze a project and generate PM2 service commands for detected frontend, backe
- `/pr` — Create a GitHub PR from current branch with unpushed commits — discovers templat
- `/project-init` — Detect a project's stack and produce a dry-run ECC onboarding plan using the rep
- `/projects` — List known projects and their instinct statistics
- `/promote` — Promote project-scoped instincts to global scope
- `/prp-commit` — Quick commit with natural language file targeting — describe what to commit in p
- `/prp-implement` — Execute an implementation plan with rigorous validation loops
- `/prp-plan` — Create comprehensive feature implementation plan with codebase analysis and patt
- `/prp-pr` — Create a GitHub PR from current branch with unpushed commits — discovers templat
- `/prp-prd` — Interactive PRD generator - problem-first, hypothesis-driven product spec with b
- `/prune` — Delete pending instincts older than 30 days that were never promoted
- `/python-review` — Comprehensive Python code review for PEP 8 compliance, type hints, security, and
- `/quality-gate` — Run the ECC quality pipeline for a file or project scope and report remediation 
- `/refactor-clean` — Safely identify and remove dead code with verification after each change.
- `/resume-session` — Load the most recent session file from ~/.claude/session-data/ and resume work w
- `/review-pr` — Comprehensive PR review using specialized agents
- `/rust-build` — Fix Rust build errors, borrow checker issues, and dependency problems incrementa
- `/rust-review` — Comprehensive Rust code review for ownership, lifetimes, error handling, unsafe 
- `/rust-test` — Enforce TDD workflow for Rust. Write tests first, then implement. Verify 80%+ co
- `/santa-loop` — Adversarial dual-review convergence loop — two independent model reviewers must 
- `/save-session` — Save current session state to a dated file in ~/.claude/session-data/ so work ca
- `/security-scan` — Run AgentShield against agent, hook, MCP, permission, and secret surfaces.
- `/sessions` — Manage Claude Code session history, aliases, and session metadata.
- `/setup-pm` — Configure your preferred package manager (npm/pnpm/yarn/bun)
- `/skill-create` — Analyze local git history to extract coding patterns and generate SKILL.md files
- `/skill-health` — Show skill portfolio health dashboard with charts and analytics
- `/test-coverage` — Analyze coverage, identify gaps, and generate missing tests toward the target th
- `/update-codemaps` — Scan project structure and generate token-lean architecture codemaps.
- `/update-docs` — Sync documentation from source-of-truth files such as scripts, schemas, routes, 

### Skills (.claude/skills/) — 233 total

<details><summary>Click to expand full skill list</summary>

- `accessibility`
- `agent-architecture-audit`
- `agent-eval`
- `agent-harness-construction`
- `agent-introspection-debugging`
- `agent-payment-x402`
- `agent-sort`
- `agentic-engineering`
- `agentic-os`
- `ai-first-engineering`
- `ai-regression-testing`
- `android-clean-architecture`
- `angular-developer`
- `api-connector-builder`
- `api-design`
- `architecture-decision-records`
- `article-writing`
- `automation-audit-ops`
- `autonomous-agent-harness`
- `autonomous-loops`
- `backend-patterns`
- `benchmark`
- `blender-motion-state-inspection`
- `blueprint`
- `brand-voice`
- `browser-qa`
- `bun-runtime`
- `canary-watch`
- `carrier-relationship-management`
- `cisco-ios-patterns`
- `ck`
- `claude-devfleet`
- `click-path-audit`
- `clickhouse-io`
- `code-tour`
- `codebase-onboarding`
- `coding-standards`
- `compose-multiplatform-patterns`
- `configure-ecc`
- `connections-optimizer`
- `content-engine`
- `content-hash-cache-pattern`
- `context-budget`
- `continuous-agent-loop`
- `continuous-learning-v2`
- `continuous-learning`
- `cost-aware-llm-pipeline`
- `cost-tracking`
- `council`
- `cpp-coding-standards`
- `cpp-testing`
- `crosspost`
- `csharp-testing`
- `customer-billing-ops`
- `customs-trade-compliance`
- `dart-flutter-patterns`
- `dashboard-builder`
- `data-scraper-agent`
- `database-migrations`
- `deep-research`
- `defi-amm-security`
- `deployment-patterns`
- `design-system`
- `django-celery`
- `django-patterns`
- `django-security`
- `django-tdd`
- `django-verification`
- `dmux-workflows`
- `docker-patterns`
- `documentation-lookup`
- `dotnet-patterns`
- `e2e-testing`
- `ecc-guide`
- `ecc-tools-cost-audit`
- `email-ops`
- `energy-procurement`
- `enterprise-agent-ops`
- `error-handling`
- `eval-harness`
- `evm-token-decimals`
- `exa-search`
- `fal-ai-media`
- `fastapi-patterns`
- `finance-billing-ops`
- `flox-environments`
- `flutter-dart-code-review`
- `foundation-models-on-device`
- `frontend-design-direction`
- `frontend-patterns`
- `frontend-slides`
- `fsharp-testing`
- `gan-style-harness`
- `gateguard`
- `git-workflow`
- `github-ops`
- `golang-patterns`
- `golang-testing`
- `google-workspace-ops`
- `graphify`
- `healthcare-cdss-patterns`
- `healthcare-emr-patterns`
- `healthcare-eval-harness`
- `healthcare-phi-compliance`
- `hermes-imports`
- `hexagonal-architecture`
- `hipaa-compliance`
- `homelab-network-readiness`
- `homelab-network-setup`
- `homelab-pihole-dns`
- `homelab-vlan-segmentation`
- `homelab-wireguard-vpn`
- `hookify-rules`
- `inventory-demand-planning`
- `investor-materials`
- `investor-outreach`
- `ios-icon-gen`
- `iterative-retrieval`
- `java-coding-standards`
- `jira-integration`
- `jpa-patterns`
- `knowledge-ops`
- `kotlin-coroutines-flows`
- `kotlin-exposed-patterns`
- `kotlin-ktor-patterns`
- `kotlin-patterns`
- `kotlin-testing`
- `laravel-patterns`
- `laravel-plugin-discovery`
- `laravel-security`
- `laravel-tdd`
- `laravel-verification`
- `lead-intelligence`
- `liquid-glass-design`
- `llm-trading-agent-security`
- `logistics-exception-management`
- `make-interfaces-feel-better`
- `manim-video`
- `market-research`
- `mcp-server-patterns`
- `messages-ops`
- `mle-workflow`
- `motion-advanced`
- `motion-foundations`
- `motion-patterns`
- `motion-ui`
- `mysql-patterns`
- `nanoclaw-repl`
- `nestjs-patterns`
- `netmiko-ssh-automation`
- `network-bgp-diagnostics`
- `network-config-validation`
- `network-interface-health`
- `nextjs-turbopack`
- `nodejs-keccak256`
- `nutrient-document-processing`
- `nuxt4-patterns`
- `openclaw-persona-forge`
- `opensource-pipeline`
- `perl-patterns`
- `perl-security`
- `perl-testing`
- `plan-orchestrate`
- `plankton-code-quality`
- `postgres-patterns`
- `prisma-patterns`
- `product-capability`
- `product-lens`
- `production-audit`
- `production-scheduling`
- `project-flow-ops`
- `prompt-optimizer`
- `python-patterns`
- `python-testing`
- `pytorch-patterns`
- `quality-nonconformance`
- `quarkus-patterns`
- `quarkus-security`
- `quarkus-tdd`
- `quarkus-verification`
- `ralphinho-rfc-pipeline`
- `recsys-pipeline-architect`
- `redis-patterns`
- `regex-vs-llm-structured-text`
- `remotion-video-creation`
- `repo-scan`
- `research-ops`
- `returns-reverse-logistics`
- `rules-distill`
- `rust-patterns`
- `rust-testing`
- `safety-guard`
- `santa-method`
- `scientific-db-pubmed-database`
- `scientific-db-uspto-database`
- `scientific-pkg-gget`
- `scientific-thinking-literature-review`
- `scientific-thinking-scholar-evaluation`
- `search-first`
- `security-bounty-hunter`
- `security-review`
- `security-scan`
- `seo`
- `skill-comply`
- `skill-scout`
- `skill-stocktake`
- `social-graph-ranker`
- `springboot-patterns`
- `springboot-security`
- `springboot-tdd`
- `springboot-verification`
- `strategic-compact`
- `swift-actor-persistence`
- `swift-concurrency-6-2`
- `swift-protocol-di-testing`
- `swiftui-patterns`
- `tdd-workflow`
- `team-builder`
- `terminal-ops`
- `tinystruct-patterns`
- `token-budget-advisor`
- `ui-demo`
- `ui-to-vue`
- `uncloud`
- `unified-notifications-ops`
- `verification-loop`
- `video-editing`
- `videodb`
- `visa-doc-translate`
- `vite-patterns`
- `windows-desktop-e2e`
- `workspace-surface-audit`
- `x-api`

</details>

### Subagents (.claude/agents/) — 60 total

<details><summary>Click to expand full agent list</summary>

- `a11y-architect`
- `architect`
- `build-error-resolver`
- `chief-of-staff`
- `code-architect`
- `code-explorer`
- `code-reviewer`
- `code-simplifier`
- `comment-analyzer`
- `conversation-analyzer`
- `cpp-build-resolver`
- `cpp-reviewer`
- `csharp-reviewer`
- `dart-build-resolver`
- `database-reviewer`
- `django-build-resolver`
- `django-reviewer`
- `doc-updater`
- `docs-lookup`
- `e2e-runner`
- `fastapi-reviewer`
- `flutter-reviewer`
- `fsharp-reviewer`
- `gan-evaluator`
- `gan-generator`
- `gan-planner`
- `go-build-resolver`
- `go-reviewer`
- `harmonyos-app-resolver`
- `harness-optimizer`
- `healthcare-reviewer`
- `homelab-architect`
- `java-build-resolver`
- `java-reviewer`
- `kotlin-build-resolver`
- `kotlin-reviewer`
- `loop-operator`
- `mle-reviewer`
- `network-architect`
- `network-config-reviewer`
- `network-troubleshooter`
- `opensource-forker`
- `opensource-packager`
- `opensource-sanitizer`
- `performance-optimizer`
- `planner`
- `pr-test-analyzer`
- `python-reviewer`
- `pytorch-build-resolver`
- `refactor-cleaner`
- `rust-build-resolver`
- `rust-reviewer`
- `security-reviewer`
- `seo-specialist`
- `silent-failure-hunter`
- `swift-build-resolver`
- `swift-reviewer`
- `tdd-guide`
- `type-design-analyzer`
- `typescript-reviewer`

</details>
