# Contributing

Thanks for helping improve the Research Diploma auth service.

## Code of Conduct

This project follows the Code of Conduct in [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).

## Getting set up

Prerequisites:

- Node.js (recommended 20+)
- pnpm
- A running database instance (see README for details)

Install dependencies:

```bash
pnpm install
```

Create your environment file:

- Copy `.env.example` to `.env` and fill in the required values (see [README.md](README.md))

Run locally:

```bash
pnpm dev
```

## Branching & workflow

- Branch from `staging`.
- Use short, descriptive branch names, e.g. `fix/token-expiry`, `feat/refresh-endpoint`.
- Keep PRs focused (one feature/fix per PR when possible).

## Contribution flow (GitHub Actions)

This repository includes workflows under `.github/workflows/` that automate parts of the contribution process (issue assignment, project-board status moves, and PR state signals). To avoid fighting the automation, follow the flow below.

### 1) Pick an issue and claim it

Before you start coding:

- Ensure the issue has been added to the GitHub Project named **"Research Diploma"** by maintainers.
- Ensure the issue is in **Status = Unclaimed**.

To claim the issue, comment exactly:

```text
claim
```

Rules:

- The comment must be only `claim` (case-insensitive; whitespace/newlines are ignored).
- If successful, you'll be assigned to the issue and the project Status will move to **Claimed**.

### 2) If you can't continue, disclaim the issue

Comment exactly:

```text
disclaim
```

If you are assigned, automation will unassign you and move the project Status back to **Unclaimed**.

### 3) Open a PR and link it to the issue

- Create your branch from `staging`.
- Open a PR targeting `staging`.

Recommended:

- Add `Closes #<issue-number>` in the PR description.

If you are assigned to the issue, you can also link the PR by commenting on the **issue**:

```text
propose #<pr-number>
```

Examples that work:

```text
propose #12
propose PR #12
```

If successful, automation will:

- Append `Closes #<issue-number>` to the PR body
- Move the issue on the project board to **In Progress**

### 4) Withdraw/unlink a PR (if needed)

If you need to detach a PR from the issue, comment on the **issue**:

```text
withdraw #<pr-number>
```

If successful, automation removes the `Closes #<issue-number>` line and moves the issue back to **Claimed**.

### 5) Signal review state on the PR

On the **pull request**, you can comment:

```text
awaiting-review
```

This will:

- Add the `awaiting-review` label (and remove `awaiting-author` if present)
- Move the linked issue on the project board to **In Review** (requires `Closes #<issue-number>` in the PR body)

If you need changes and want to signal the opposite state, comment:

```text
awaiting-author
```

This will add the `awaiting-author` label (and remove `awaiting-review` if present).

## Coding standards

### TypeScript

- Keep types explicit at module boundaries (request payloads, service interfaces).
- Avoid `any` unless you have a strong reason.

### API conventions

- Follow the existing route structure in `src/routes/`.
- Use existing middleware patterns for auth and validation.

## Pull request checklist

- [ ] PR targets `staging`
- [ ] Runs locally without errors
- [ ] Lint passes
- [ ] Updated docs (README/Swagger) if behavior or env vars changed

## Security

- Do not commit secrets (API keys, JWT secrets, database credentials).
- If you discover a security issue, avoid opening a public issue with exploit details; share a minimal report with maintainers instead.
