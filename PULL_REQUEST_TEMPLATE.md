## What does this PR do?
<!-- One or two lines. Cite IDs, e.g. SD-121, TR-513, PR-085. -->

## Checklist
- [ ] IDs cited (SD / TR / PR / BRD)
- [ ] Only files listed for the task (Section 15) changed, or the extras are explained
- [ ] Tests added or updated
- [ ] `make check` is green locally
- [ ] No money rounding outside `core/money.py`
- [ ] No new `.env` variable without `.env.example` and the Section 9 update
- [ ] Migration follows SD-240
- [ ] Nothing in Section 14.3 changed without an accepted SCR
- [ ] AI session tool named: claude-code / cursor / copilot / codex / none
- [ ] Screenshots attached for UI changes
- [ ] Targets the right branch: feature to `dev`, `dev` to `uat`, `uat` to `master`

Threat model impact: none / see SECCR-##

## Money self-review
<!-- Only for ledger, payouts, CSV parsing or apply, lock, core/money.py. Leave unticked otherwise. -->
- [ ] MC / HG cases touched are listed here:
- [ ] No rounding or float outside `core/money.py`; platform share first, 6 dp half-even, payout USD rounded down with remainder carried, INR half-up (BR-014)
- [ ] Append-only, locked-month and payout guards unchanged, or new DB tests added
- [ ] Idempotency and audit rows kept
- [ ] Migrations are expand-only
- [ ] Any change to the recompute export is in `docs/recompute/FORMAT.md`, and Dev B is told the format changed (never the code)
- [ ] Golden, hand-worked and money tests are green on this commit

## Independent AI review
<!-- Money paths only. -->
- Tool / model:
- [ ] Fresh session, started in a clone without `tools/recompute/`, given only this diff, the specs and `docs/ai/money-review.md`
- Findings:
- All findings resolved: yes
