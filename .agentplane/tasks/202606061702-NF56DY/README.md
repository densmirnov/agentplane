---
id: "202606061702-NF56DY"
title: "Fix upstream issue #4463: Release evidence PR can require a no-op commit before required PR verification appears"
status: "DOING"
priority: "med"
owner: "CODER"
revision: 5
origin:
  system: "manual"
depends_on: []
tags:
  - "github-issue"
verify: []
plan_approval:
  state: "approved"
  updated_at: "2026-06-06T17:03:14.519Z"
  updated_by: "ORCHESTRATOR"
  note: null
verification:
  state: "pending"
  updated_at: null
  updated_by: null
  note: null
  attempts: 0
commit: null
comments:
  -
    author: "CODER"
    body: "Start: investigating and fixing upstream issue #4463 in the dedicated branch_pr worktree, then running the targeted release-evidence verification steps."
events:
  -
    type: "status"
    at: "2026-06-06T17:04:37.855Z"
    author: "CODER"
    from: "TODO"
    to: "DOING"
    note: "Start: investigating and fixing upstream issue #4463 in the dedicated branch_pr worktree, then running the targeted release-evidence verification steps."
doc_version: 3
doc_updated_at: "2026-06-06T17:04:37.855Z"
doc_updated_by: "CODER"
description: "Resolve https://github.com/basilisk-labs/agentplane/issues/4463"
sections:
  Summary: |-
    Fix upstream issue #4463: Release evidence PR can require a no-op commit before required PR verification appears

    Resolve https://github.com/basilisk-labs/agentplane/issues/4463
  Scope: |-
    - In scope: Resolve https://github.com/basilisk-labs/agentplane/issues/4463.
    - Out of scope: unrelated refactors not required for "Fix upstream issue #4463: Release evidence PR can require a no-op commit before required PR verification appears".
  Plan: |-
    1. Inspect the release evidence PR creation path and identify why the initial evidence branch head can miss the required GitHub Actions `PR verification` check.
    2. Update the release publish/evidence workflow so the first evidence branch head naturally produces the required verification signal without a manual no-op recovery commit.
    3. Add or adjust targeted contract tests for the release evidence branch and PR verification path, then run focused verification and record the results.
  Verify Steps: |-
    1. Run the targeted release evidence contract tests covering evidence branch CI dispatch and release-evidence PR creation. Expected: the workflow contract reflects the path that should produce `PR verification` on the initial evidence branch head.
    2. Run the targeted release/CI verification for the changed codepath after the fix. Expected: all touched tests pass without requiring a manual follow-up commit or unstated recovery step.
    3. Review the final diff and task Findings against upstream issue #4463. Expected: the fix stays scoped to release-evidence verification behavior and any residual operational caveats are explicit.
  Verification: |-
    <!-- BEGIN VERIFICATION RESULTS -->
    <!-- END VERIFICATION RESULTS -->
  Rollback Plan: |-
    - Revert task-related commit(s).
    - Re-run required checks to confirm rollback safety.
  Findings: ""
id_source: "generated"
---
## Summary

Fix upstream issue #4463: Release evidence PR can require a no-op commit before required PR verification appears

Resolve https://github.com/basilisk-labs/agentplane/issues/4463

## Scope

- In scope: Resolve https://github.com/basilisk-labs/agentplane/issues/4463.
- Out of scope: unrelated refactors not required for "Fix upstream issue #4463: Release evidence PR can require a no-op commit before required PR verification appears".

## Plan

1. Inspect the release evidence PR creation path and identify why the initial evidence branch head can miss the required GitHub Actions `PR verification` check.
2. Update the release publish/evidence workflow so the first evidence branch head naturally produces the required verification signal without a manual no-op recovery commit.
3. Add or adjust targeted contract tests for the release evidence branch and PR verification path, then run focused verification and record the results.

## Verify Steps

1. Run the targeted release evidence contract tests covering evidence branch CI dispatch and release-evidence PR creation. Expected: the workflow contract reflects the path that should produce `PR verification` on the initial evidence branch head.
2. Run the targeted release/CI verification for the changed codepath after the fix. Expected: all touched tests pass without requiring a manual follow-up commit or unstated recovery step.
3. Review the final diff and task Findings against upstream issue #4463. Expected: the fix stays scoped to release-evidence verification behavior and any residual operational caveats are explicit.

## Verification

<!-- BEGIN VERIFICATION RESULTS -->
<!-- END VERIFICATION RESULTS -->

## Rollback Plan

- Revert task-related commit(s).
- Re-run required checks to confirm rollback safety.

## Findings
