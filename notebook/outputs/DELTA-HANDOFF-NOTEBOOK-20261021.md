# Delta handoff — Living Energy Research Notebook

Date: 2026-10-21  
Purpose: transition scientific memory, provenance and epistemic-audit responsibility. Do not infer authorization for new research from this handoff.

## Authoritative locations

- Canonical vault: `/Users/prateek/Documents/Codex/2026-09-23/referenced-chatgpt-conversation-this-is-an-2/outputs/Living Energy Research`
- Workflow: canonical `AGENT-WORKFLOW.md`
- Delta Notebook workspace: `/Users/prateek/Documents/Codex/2026-10-21/living-energy-delta/notebook`
- Living Energy skill: `/Users/prateek/.codex/skills/living-energy-research/SKILL.md`
- Compact state: `00_state/research_state.md`, `current_direction.md`, `priority_queue.md`, `recent_changes.md`
- IDs: `object-registry.json`; aliases/schema: `Schema and ID Crosswalk.md`
- Provenance/indexes: `08 Maintenance/Source Register.md`, `Chronology and Changelog.md`, `Team Handoff Queue.md`, `Research Team.md`
- Canonical transition note: `11 Handoffs/NOTEBOOK-20261021-Delta-transition.md`

The unpacked vault is authoritative. ZIP files are historical snapshots. Bulk simulation outputs live in the vault workspace but are deliberately excluded from its text-only Git history.

## Roles and research boundary

| Role | Task ID | Authority |
|---|---|---|
| Orchestrator | `01a0eda6-6673-7530-8767-a9129e5d3b0e` | Priorities, scope, commissions and direction |
| Theory | `01a0edaa-ba45-72f3-9a87-537caf29ad83` | Literature, derivation and interpretation |
| Simulation | `01a0d02b-9671-7563-b932-b428c7c9ba2b` | Implementation, tests and run artifacts |
| Notebook | `01a0d03b-bae4-7f20-9645-52b6b1acf4a7` | Shared state, IDs, provenance and epistemic audit |

Central objective: test whether biological energy-management principles can improve antimatter generation, capture, storage, transport or conversion. Biology is a source of architectural hypotheses, not evidence of shared microscopic physics. ETC chemistry and hadronic antiproton production do not share rate laws.

## Current transition state

FTFP_BERT is the future primary/default list under D014. This is a continuity standard, not physical validation. Completed SIM008 retains QGSP_BIC and its factor-2.60 discrepancy as a permanent model-systematic warning.

SIM009 is the active staged E910 validation under D015. Late transition reconciliation verified the Delta Simulation packet and canonical audit artifacts. Canonical status is now:

- Stage A computational occurrence-bias gate PASS;
- Stage B blocked;
- physical-validation level null;
- independent source evaluation closed;
- thick-Ir, geometry, new energy and field-architecture work closed.

Highest-priority next action: close Stage B readiness gaps and obtain an explicit Orchestrator release. Passing the Stage A estimator audit is not E910 validation.

## Registry and identifiers

The canonical registry has 70 unique objects. Next IDs are Q011, H006, A008, C016, SIM010, E010, D016, F001 and X001. Never allocate from memory. Atomically update `object-registry.json` and the crosswalk; never reuse IDs.

## Decisions D010–D015

| ID | Meaning |
|---|---|
| D010 | Adopt four-role workflow; Orchestrator chooses direction and Notebook owns canonical records/IDs |
| D011 | Freeze H001 R/P/D baseline; preserved, deferred and still SPECULATIVE |
| D012 | Require compact-source census before architecture comparison |
| D013 | Commission SIM008 bounded development; completed/audited without physical validation |
| D014 | Make FTFP_BERT the future default while preserving SIM008's QGSP_BIC warning |
| D015 | Commission staged SIM009 E910 validation; Stage B conditional on Stage A passage |

D014 does not rewrite SIM008 as one-list work. D015 authorizes only the bounded E910 study.

## Claims, hypotheses and evidence

H001–H005 remain SPECULATIVE: terminal-yield coupling, controlled modulation, buffering, ensemble feedback and ETC gating. No hypothesis is currently promoted by SIM008 or SIM009.

- C008 REJECTED: ETC and hadronic production do not share microscopic rate laws.
- C010 UNRESOLVED: no demonstration that biological principles improve real antiproton-source performance.
- C012 SUPPORTED within an uncalibrated model: added telegraph noise reduced ATP output in RUN-001.
- C013 SUPPORTED within its model: staging improved capture per pulse but not per assigned time.
- C014 SUPPORTED as bounded execution: RUN-002 scored 113 exits/100,000 primaries; not a facility yield.
- C015 SUPPORTED as implementation check: GillesPy2/original ETC means agreed within sampling uncertainty.

E008/E009 retain legacy E2 model-artifact labels and current new evidence level `null`. Legacy E2 is not Level C. No F### finding or X### contradiction has been allocated.

## SIM008 result and permanent limits

Paths: `07_simulations/SIM008/README.md`, `conclusion.md`, `processed_results/final_audit.json`, `11 Handoffs/SIM-20261005-SIM008-development-completion.md` and `THEORY-20261006-SIM008-interpretation-and-validation-gate.md`.

Audit: 38 included cases, 1.9M included primaries, 418 verified files, 12,499,477,023 compressed CSV bytes, no included failures. Three hundred pilots and one interrupted 47,110-event 8 GeV partial are excluded and preserved.

Bounded result: lower-energy advantage was NOT_SUPPORTED in the fixed 3 mm-radius × 50 mm Ir model. At 25.08 GeV/100k primaries per list, FTFP_BERT selected 26 and QGSP_BIC 10; rate ratio 2.60, approximate interval 1.25–5.39. The spread enters mainly at creation. The 25.08 GeV point is an upper scanned boundary, not a validated optimum, and remains a two-list envelope.

Sugaya produced zero raw selected events and E910 two total, so no physical-validation level was assigned. None of eight optimization triggers fired. Model disagreement and sparse yield remain limitations.

## SIM009 frozen scope

Paths: `07_simulations/SIM009/README.md`, `config/experimental_observable.md`, `config/stage_a_gate.md`, `config/stage_a_frozen_manifest_v2.json`, and `11 Handoffs/ORCH-20261006-SIM009-E910-validation-commission.md`.

Comparison: FTFP_BERT p+Au at 11.397 and 16.587 GeV; strict `1<y_lab<2`, `0.010<pT<0.800 GeV/c`, `p<3.5 GeV/c`; corrected antiproton multiplicity per minimum-bias inelastic event.

Digitized final-paper values:

- low: `1.4122e-4 ± 4.120e-5` per event;
- high: `4.4383e-4 ± 3.391e-5` per event;
- ratio: 3.1428;
- no published covariance; diagonal total-error approximation explicitly frozen.

Stage A bias gate requires analog/factor-10 agreement at `|z|≤1.96` for inelastic probability, creation per weighted inelastic event and accepted yield; weighted KS `p≥0.05` for created-antiproton y/pT/p; analog ≥10 creations; biased creation `N_eff≥50`; accepted `N_eff≥10`; weight closure `1e-12`; positive weights ≤1.

Latest execution artifacts:

- analog and factor-10 smoke runs at 10k each;
- completed 10M analog audit directory (`exit_code: 0`);
- five completed independent 1M factor-10 directories (`exit_code: 0` each);
- earlier monolithic 5M factor-10 attempt marked ABORTED, unknown processed count, excluded from every estimator.

Late audit result: the five successful biased batches were combined and deterministic reanalysis reproduced `processed_results/stage_a_bias_audit.json` byte-for-byte. All frozen computational gates pass: yield/probability z values 1.744, 0.609 and 0.356; weighted KS p values 0.605, 0.219 and 0.671; biased creation/accepted ESS 390.657/159.459; exact closure; maximum creation weight 0.121992. Audit JSON SHA-256 is `6c38fede661bb846999104121e5a399be0c7cb578ca63df64dd7de1c46357188`.

Preserve the aborted attempt, historical manifest/config drift, 12 residual `fate=tracking` records (weight 1.3155), unset explicit Geant4 data-library paths and the missing numerical decisive-incompatibility rule. Stage B remains unreleased.

Conditional Stage B only after recorded PASS: 5M high plus 16M low initial, caps 10M/32M and 42M total, stop at `N_eff≥200` per cell or decisive incompatibility. Use aggregate/accepted-event output, not full all-species ledgers. Pass rule: log-ratio `z≤1.96` and both absolute yields compatible with combined published 95% intervals; UNRESOLVED if corrected uncertainty is unusable.

## Provenance gaps

- Original ChatGPT conversation `6ab1f759-acb8-83ea-8379-760ec8265de0` has two truncated assistant tails and missing generated attachments.
- The legacy ODE/trap package was not recovered; SIM005 records the gap.
- Some literature reading was performed by Theory and not independently repeated by Notebook; preserve recorded reading depth.
- E910 values are digitized from final-paper Figure 3; covariance is unavailable.
- Bulk CSV/JSON/PDF data are outside Git. Consult frozen manifests/hashes.
- The aborted SIM009 directory has no reliable processed count and must never be merged.
- Raw execution success is not bias passage, validation or evidence promotion.

## Workflow rules

1. Start by reading this handoff, `AGENT-WORKFLOW.md` and the four compact state files.
2. Orchestrator chooses/commissions research; Notebook reconciles state and IDs.
3. Use structured handoffs in `11 Handoffs`.
4. Treat Theory as interpretation and Simulation as model evidence subject to validity.
5. Keep status, confidence and evidence level distinct; never promote analogy or uncalibrated runs.
6. Preserve null, negative, failed, aborted and contradictory results append-only.
7. Separate sampling, parameter, model, numerical and experimental uncertainty.
8. Preserve software/data versions, code/config hashes, seeds, denominators, zeros and sibling dependence.
9. Use Git for text-state changes; do not add bulk raw outputs.
10. Large computation and physical/hazardous experiments require explicit human authorization. No physical experiment is authorized.

## Exact checklist for Delta

- [ ] Read workflow, compact state, D014/D015, SIM009 README/gate/observable/v2 manifest.
- [ ] Check for a newer Simulation handoff before acting.
- [ ] Verify the Stage A packet SHA-256 `29dbad6b521ea6a17d764bbb96cddd8b314243ce0e8dba6607c6797f7d17eeae` and canonical audit hashes.
- [ ] Preserve/exclude the aborted monolithic 5M directory.
- [ ] Define the numerical decisive-incompatibility early-stop boundary.
- [ ] Implement/verify the two-energy Stage B analyzer and cap-limited outcomes.
- [ ] Resolve or explicitly bound the 12 residual tracking records.
- [ ] Create a new immutable Stage B manifest; do not overwrite Stage A manifests.
- [ ] Obtain explicit Orchestrator Stage B release tied to D015 before execution.
- [ ] Do not open QGSP_BIC, thick-Ir, geometry, new energy, independent source evaluation or architecture work.
- [ ] Do not assign physical-validation level until Stage B completion is audited.
- [ ] Update compact state, SIM009, registries/indexes, provenance and chronology; commit locally and report hash.

## Git baseline

Canonical transition commit before late reconciliation: `a11412e` (`notebook: hand off canonical state to Delta`). Earlier key commits: `9d0a584`, `3b1eaa4`, `de6e7ad`, `d84bd64`, `a5b30f7`, `ac5d40d`.

The canonical transition commit is reported by the sending Notebook task after save.
