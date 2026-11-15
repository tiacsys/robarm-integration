## What and why

<!-- What does this PR change, and why? Link the issue it closes: "Closes #123". -->

## Checks

- [ ] `curatrix check robarm-integration --stage local` passes (run from the workspace root, with CAD content where the repo has it)
- [ ] New IDs come from the ledger (`curatrix ids fix robarm-integration`); no placeholders are left
- [ ] Generated files are regenerated and committed (`curatrix gen all robarm-integration`)
- [ ] For a change across repos: the same branch name is used in every repo, and the other PRs are linked here
- [ ] HIL evidence is recorded only from `main` or baseline commits (runs from PR branches are previews)

## Notes for the reviewer

<!-- Anything the reviewer should look at first, open questions, follow-up work. -->
