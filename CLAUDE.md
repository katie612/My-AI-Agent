# AI Solopreneur

A local Claude-powered project assistant — browser chat plus a visual n8n agent — that
runs entirely as ordinary Node.js processes on the user's own machine. Nothing deploys to
the cloud in this release.

This is also **teaching material**. The audience is non-technical solopreneurs doing their
first technical project, following `docs/GETTING_STARTED.md`. That audience constraint
drives most of the decisions below.

Node 24.x pinned. n8n 2.30.5. Local release `v0.2.0`.

## Audience rules

- Write for someone who has never used a terminal. Every instruction names the thing, the
  click, the success check, and the recovery path if it fails.
- No unexplained jargon. If a term must appear, define it at first use.
- Never assume a global install. Setup selects or downloads the reviewed Node/npm pair
  into the project.
- Every destructive or state-changing action is confirmation-gated, and "yes" is not
  sufficient — the confirmation must be exact.

## Commands

Run via `npm run <script>`, all of which delegate to `scripts/local.mjs`:

`setup` · `start` · `stop` · `restart` · `status` · `diagnose` · `preflight` ·
`import-workflows` · `export-workflows` · `sync-skills` · `backup` · `reset`

`.command` (macOS) and `.cmd` (Windows) wrappers at the repo root exist so learners can
double-click instead of using a terminal. **Any new script needs both wrappers**, or
Windows learners are stranded.

## Docs

`docs/` is the product, not an afterthought. Key entries:

- `GETTING_STARTED.md` — the beginner path; the single most important file here
- `LOCAL_SETUP.md`, `LOCAL_OPERATIONS.md`, `TROUBLESHOOTING.md` — the operational trio
- `PRODUCT_BASELINE.md`, `GO_NO_GO.md` — what "done" means
- `PILOT_RUNBOOK.md`, `PILOT_FINDINGS.md` — pilot process and what came back
- `CHAT_CONTRACT.md`, `SAFE_WRITE_CONFIRMATION.md` — behavioural contracts for the chat
- `INSTRUCTOR_CHECKLIST.md`, `COURSE_GUIDE.md`, `WORKSHOP_PREREQUISITES.md` — teaching

When behaviour changes, update the matching doc in the same commit. A stale instruction in
this repo strands a learner who has no way to diagnose it.

## Change control

`CHANGELOG.md` and `VERSION` are maintained — see `docs/RELEASE.md` and
`docs/FEEDBACK_AND_CHANGE_CONTROL.md` before cutting a release.

## Secrets

`.env` is real and local. `.env.example` is the committed template. Never commit `.env`,
never print API keys into docs, screenshots, or terminal output.
