# Agent, Security, and Contribution Context

## Operating model

- This public repository is maintained by a single owner and contains reusable source; private operational deployments retain their own owners and authority.
- No mandatory review, CODEOWNERS, or team-approval gates are required for merge.
- Recovery remains possible via repository owner override and branch protection exceptions.

## Current automation posture

- Continuous checks:
  - `validate` workflow (`validate (RepositoryHygiene)`, `validate (SourceControlReady)`)
  - `workflow-lint`
  - `secret scan`
  - `codeql` (`analyze`)
  - `coverage` (Codecov upload + OIDC)
- Bot workflow:
  - Renovate inherits from `github>edithatogo/renovate-config`
  - Dependabot is intentionally removed once Renovate is active.

## Required review of changes

- Keep raw data, credentials, and environment secrets out of git.
- Use the one-command quality gate before merge.
- Keep changes minimal and reproducible across Windows and GitHub-hosted runners.

## Qualified suite CI rollout

The shared CareOps security job replaces duplicate tool installation while retaining
the existing lint workflows and secret scan gate names until hosted protection
migration is verified. All current-head checks must pass before normal merge;
owner bypass is not the suite delivery route. Renovate remains the sole updater,
with immutable action digests and no automatic promotion. Runtime development
candidates require source validation and exact artifact integrity evidence.
Billing refusals are not executed test failures or successful qualification.

## Portable suite delivery

Read README.md and .careops/module.json for the existing source/native queue and
shared standards. Retain exact pins, current-head CI gates and publication
boundaries. Use only fictional inputs in portable source; private bindings,
records and native exports remain outside Git. Preserve existing component IDs
and publisher/logical names. Source packaging never establishes native operation.
Evaluate the shared preferred structured-document route before a new generator.
