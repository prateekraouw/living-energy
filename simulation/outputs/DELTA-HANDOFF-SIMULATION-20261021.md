# Delta Simulation handoff — 2026-10-21

## Immediate state

This packet transfers the Simulation role to Delta. It audits existing artifacts only. No SIM009 Stage B cell, new physics run, biology run, geometry change, additional energy, QGSP_BIC job, thick-Ir job, source evaluation or architecture job was launched during the transition.

The canonical vault remains:

`/Users/prateek/Documents/Codex/2026-09-23/referenced-chatgpt-conversation-this-is-an-2/outputs/Living Energy Research`

The new Simulation workspace is:

`/Users/prateek/Documents/Codex/2026-10-21/living-energy-delta/simulation`

Shared state, IDs and decisions remain Notebook/Orchestrator owned. Delta should write local work in the new repository and submit structured packets rather than directly reconciling canonical ledgers.

The exact computational status is:

- **SIM008:** completed bounded development; 1,900,000 included primaries across 38 cases; final artifact audit passed. It supplies numerical development evidence and a material model-disagreement warning, with no physical-validation level.
- **SIM009 Stage A raw execution:** complete. One 10,000,000-primary analog case and five successful 1,000,000-primary factor-10 cases exist, all with exit code 0.
- **SIM009 Stage A analysis:** now combined and reproduced byte for byte. Every predeclared occurrence-bias gate passes.
- **SIM009 Stage A adjudication:** the computational gate result exists, but Notebook and Orchestrator have not yet reconciled the canonical status or issued a Stage B release record.
- **SIM009 Stage B:** never launched. It must remain unlaunched until Delta/Orchestrator explicitly releases it after reviewing this packet and the limitations below.
- **Hadronic standard:** `FTFP_BERT` remains the future default under D014. This is an operational choice and is **not physical validation**.

## Scientific boundary

The biological and hadronic models do not share microscopic physics. ETC electron transfer is governed by molecular redox energetics, coupling/tunnelling, conformational kinetics and membrane electrochemistry. Antiproton creation is governed by hadronic production, nuclear cascades, conservation laws, formation and absorption. Shared stochastic-network language is an architectural/formal analogy only.

For the current well-mixed discrete ETC model, the preferred backend remains **GillesPy2 1.8.3 using its compiled exact C++ `SSACSolver`**. The environment is Python 3.13.5, NumPy 2.5.3 and Matplotlib 3.11.2 at:

`/Users/prateek/Documents/Codex/2026-09-23/referenced-chatgpt-conversation-this-is-an/work/bioenv`

The custom direct Gillespie solver remains an independent implementation check. GillesPy2 is the best fit for the current lumped reaction network, not a universal best package. Use STEPS when explicit crista geometry, surface/volume diffusion or local membrane voltage becomes part of the model; use COPASI when SBML exchange and parameter estimation become primary. No biological run is commissioned by this handoff.

## SIM008 record

### Scope and implementation

SIM008 tested whether lower proton kinetic energy improved escaped low-rigidity antiprotons per incident joule in a fixed compact iridium geometry. It used Geant4 11.3.2 patch02 with separate `FTFP_BERT` and `QGSP_BIC` results. The initial matrix contained 36 cells at 50,000 primaries each. A predeclared model-disagreement rule added one 50,000-primary batch per list at 25.08 GeV.

Included exposure was 1,900,000 primaries. Three hundred debug primaries and one interrupted 47,110-event 8 GeV partial directory are retained and excluded. The primary cap was 4,000,000 and compressed-storage cap 80 GB. SIM008 occupies approximately 13 GB; audited compressed CSV content is 12,499,477,023 bytes.

The immutable numerical record is under:

`/Users/prateek/Documents/Codex/2026-09-23/referenced-chatgpt-conversation-this-is-an-2/outputs/Living Energy Research/07_simulations/SIM008`

Key files:

- `conclusion.md`
- `config/frozen_manifest.json`
- `config/study.json`
- `config/case_matrix.json`
- `config/bias_audit.md`
- `processed_results/final_audit.json`
- `processed_results/thick_combined_summary.csv`
- `processed_results/all_view_batch_summary.csv`
- `processed_results/external_validation_summary.csv`
- `processed_results/selection_lock.json`
- `raw_results/` with commands, seeds, runtime identities and per-case manifests

The SIM008 executable SHA-256 is:

`9d89641a1e6c8316a7a64774172b3778f526435e93049ffbd92f8dfeb211fd78`

The final audit reports 418 verified manifest files and no included count/hash failures. Its excluded partial is:

`raw_results/thick-T8p0-Ir-ftfp-bert-b001-n50000__partial_interrupted_47110events`

### SIM008 result

The lower-energy advantage was **not supported within the fixed model and geometry**. At the locked 25.08 GeV upper scan boundary, after 100,000 primaries per list:

| Observable | FTFP_BERT | QGSP_BIC |
|---|---:|---:|
| selected antiprotons | 26 | 10 |
| selected per primary | 2.60e-4 | 1.00e-4 |
| 95% event-resampling interval | [1.60e-4, 3.60e-4] | [4.00e-5, 1.70e-4] |
| selected per incident joule | 6.47e4 | 2.49e4 |
| created per primary | 1.49e-3 | 5.10e-4 |
| creation-to-exit survival | 0.651 | 0.725 |
| deposition fraction | 0.0448 | 0.0394 |
| charged background per primary in the same view | 1.884 | 1.699 |
| neutral kinetic energy per primary in the same view | 0.544 GeV | 0.488 GeV |

The selected-rate ratio was 2.60 with approximate Poisson interval 1.25–5.39. The discrepancy enters mainly at creation; survival and escape-to-selection fractions are similar. It cannot be averaged into a preferred central value. QGSP_BIC crosses the installed FTF/QGS transition in this range, while FTFP_BERT remains FTF based. The data do not identify which generator is physically correct.

Sugaya validation kernels produced zero selected antiprotons at the commissioned exposure. E910 kernels produced two total, both in QGSP_BIC at 16.587 GeV. Neither result physically validated a list. The 25.08 GeV point is a development boundary candidate, not an optimum, facility prediction or system-efficiency result.

### SIM008 estimator fixes and preserved failures

The raw physics was not changed by the following analysis amendments:

1. `analysis-v1.1` replaced a dense multi-view bootstrap that failed on performance with a mathematically equivalent empirical-distribution event bootstrap.
2. `analysis-v1.2` used an asymptotic normal interval for the continuous event-mean deposition observable while retaining 5,000 event bootstraps for sparse antiproton yields and acceptances.
3. `analysis-v1.3` streamed the full-census exit ledger once into exact threshold bins, avoiding multi-gigabyte dictionary materialization and 30 rescans.

The factor-10 primary `protonInelastic` occurrence-bias method was retained. In a 5,000-primary p+Cu audit, analog and factor-10 weighted inelastic probabilities were 0.10220 ± 0.00428 and 0.09787 ± 0.00113. Factor 100 was rejected: its weighted estimate was 0.07915 ± 0.01144 and it developed a maximum interaction weight of 47.94. The charged-particle force-collision prototype is also retained as a failed approach under `model/frozen_v1/failed_approaches/`. Neither occurrence bias nor Monte Carlo seeds represent a physical source-yield enhancement.

## SIM009 specification and frozen E910 observable

SIM009 asks whether `FTFP_BERT` reproduces the E910 p+Au energy ratio and both absolute corrected yields. The two planned Stage B kinetic energies are 11.397 and 16.587 GeV, corresponding to 12.3 and 17.5 GeV/c beam momenta.

The final E910 journal paper, not the preliminary thesis table, is the numerical authority. Direct vector-coordinate digitization of Figure 3 gives:

| beam momentum | kinetic energy | corrected yield per event | plotted total 1-sigma error |
|---:|---:|---:|---:|
| 12.3 GeV/c | 11.397 GeV | 1.4122e-4 | 4.120e-5 |
| 17.5 GeV/c | 16.587 GeV | 4.4383e-4 | 3.391e-5 |

The digitized high/low ratio is 3.1428, consistent with the paper's rounded 3.1. The paper supplies overall error bars but no covariance matrix. The declared approximation is diagonal total-error covariance, ordered low/high:

`[[1.69744e-9, 0], [0, 1.150e-9]]`

This likely overstates ratio uncertainty if the documented 5% matching-efficiency systematic is positively correlated. It remains an explicit limitation.

The particle-level window is strict:

- `1 < y_lab < 2`
- `0.010 < pT < 0.800 GeV/c`
- `p < 3.5 GeV/c`
- `y_lab = 0.5 ln((E+pz)/(E-pz))`

The generator boundary is antiproton first exit from the Au target. The denominator is the weighted number of primary inelastic p+Au events. The target is `G4_Au`, 2.10808 mm long and 50 mm in scoring radius, corresponding to 2.0% of Geant4's 105.404 mm nuclear interaction length and 4.07281 g/cm2. Beam momentum spread and slope spread are zero; transverse beam sigma is 0.3 mm.

E910's published yield is corrected for acceptance, efficiency, background and multiplicity-dependent trigger bias. The trigger required two hits in each of two scintillating-fiber layers. Generator normalization approximates that corrected minimum-bias inelastic-event convention but does not fold detector or trigger response. E910 estimated anti-Lambda feeddown below 5% and did not document a subtraction; SIM009 includes weak-decay feeddown only if it creates an antiproton before target exit. This boundary mismatch remains below but comparable to the reported feeddown estimate.

Primary source PDFs and hashes:

- `sources/Chemakin_2001_E910.pdf` — SHA-256 `e417ab9f066336ba7bb8db69e5365fcddc60f36b75fc00435db9f743c808ea82`
- `sources/Mioduszewski_1999_thesis.pdf` — SHA-256 `125088fcf33edbcfdd6a74382aef9a4d05a67086823caedcf69c5b6685ed4f42`

## SIM009 Stage A execution inventory

The SIM009 root is:

`/Users/prateek/Documents/Codex/2026-09-23/referenced-chatgpt-conversation-this-is-an-2/outputs/Living Energy Research/07_simulations/SIM009`

It occupies about 402 MB after creating a reproducible combined biased directory. The combined directory duplicates the five successful raw batches and can be regenerated, but it should not be deleted before Delta/Notebook has captured the present hashes.

### Included production cases

| Case | Exposure | Exit | Raw inelastic rows | Created antiprotons | First exits |
|---|---:|---:|---:|---:|---:|
| `stage-a-audit-analog-T16p587-n10000000` | 10,000,000 | 0 | 217,730 | 80 | 68 |
| `stage-a-audit-bias10-T16p587-b001-n1000000` | 1,000,000 | 0 | 198,511 | 70 | 61 |
| `...-b002-...` | 1,000,000 | 0 | 198,315 | 98 | 84 |
| `...-b003-...` | 1,000,000 | 0 | 198,365 | 59 | 42 |
| `...-b004-...` | 1,000,000 | 0 | 198,387 | 81 | 65 |
| `...-b005-...` | 1,000,000 | 0 | 197,992 | 84 | 71 |

The row counts above exclude CSV headers. Included Stage A production exposure is exactly 15,000,000 primaries. The five biased seeds are distinct and preserved in each `resolved_config.json`; the analog seeds are `[1371376288, 705100892]`.

Two 10,000-primary smoke cases also completed, with no created antiprotons. They are implementation checks and are excluded from the production estimator.

### Excluded attempt

`raw_results/stage-a-audit-bias10-T16p587-n5000000` is an interrupted monolithic attempt. It has no `execution.json`, has an `ABORTED.md` exclusion marker, and contains 56,456 sparse event rows plus 23 antiproton records before buffering/termination. The exact processed-primary count was not recorded. No row from this directory enters any result. Do not infer exposure from the sparse inelastic row count.

### Runtime and transport provenance

All included cases used:

- Geant4 `$Name: geant4-11-03-patch-02 [MT]$`
- physics list `FTFP_BERT`
- scoring mode `sim009_aggregate`
- production cut 0.1 mm
- Apple Clang 21.0.0 for the current build
- CMake 4.1.2 for the current build environment

The SIM009 executable SHA-256 is:

`4eb4749d3901dae21056ff64de8341172b5f2aee3c62dc9fe5de18b6cc1e5c7d`

Transport source hashes recorded in every included `resolved_config.json` are:

- `main.cc`: `9833ae53b0a03a67f4732b96dc61a36f00a54bbd1d536d4e28991133d8db9da6`
- `CrossSectionBiasOperator.cc`: `27ef411e24763f1690df26b0447fff9e23769cb049388c0cc6b40bd766c7ecf6`

The runtime identity records all Geant4 data environment variables as unset. The installed Geant4 configuration resolved the run, but explicit data-library paths were not captured. Preserve this as a reproducibility limitation.

No SIM009 QGSP_BIC case exists. No Stage B case exists.

## SIM009 Stage A estimator and result

The biased batches were combined with unique event-ID offsets. For event `e`, accepted yield is:

`Y = sum_e A_e / sum_e I_e`,

where `A_e` is the sum of accepted antiproton weights and `I_e` is the weighted primary-inelastic indicator. The event-level delta-method standard error is:

`SE(Y) = sqrt[N/(N-1) * sum_e (A_e - Y I_e)^2] / sum_e I_e`.

Effective sample size is `(sum w)^2 / sum(w^2)`. Created-antiproton shape agreement uses weighted empirical two-sample KS statistics in `y`, `pT` and total momentum. The predeclared gate requires all three yield/probability comparisons at `|z| <= 1.96`, all shape p-values at least 0.05, analog created count at least 10, biased creation `N_eff >= 50`, biased accepted `N_eff >= 10`, exact ledger/event weight closure, positive weights and maximum relevant track weight at most 1.

The combined audit result is:

| Metric | Analog | Factor 10 | Agreement |
|---|---:|---:|---:|
| weighted inelastic probability | 0.0217730 | 0.0218605 | z = 1.744, pass |
| creation per weighted inelastic event | 3.67428e-4 | 3.95416e-4 | z = 0.609, pass |
| accepted per weighted inelastic event | 1.51564e-4 | 1.61996e-4 | z = 0.356, pass |
| raw created | 80 | 392 | information pass |
| created `N_eff` | 80.0 | 390.657 | information pass |
| raw accepted | 33 | 160 | information pass |
| accepted `N_eff` | 33.0 | 159.459 | information pass |
| maximum creation weight | 1.0 | 0.121992 | pass |
| creation/exit weight-closure residual | 0 | 0 | pass |

Created-antiproton shape checks:

| Variable | weighted KS D | asymptotic p |
|---|---:|---:|
| rapidity | 0.09215 | 0.60497 |
| `pT` | 0.12693 | 0.21905 |
| total momentum | 0.08738 | 0.67148 |

Every predeclared Stage A factor-10 gate passes. The deterministic re-analysis JSON is byte-for-byte identical to the saved result.

Authoritative post-run analysis artifacts:

- `processed_results/stage_a_bias_audit.json` — SHA-256 `6c38fede661bb846999104121e5a399be0c7cb578ca63df64dd7de1c46357188`
- `plots/stage_a_bias_audit_shapes.png` — SHA-256 `cfac4da788439ed48677ea3170dabfe346aba21f20fd169ce00a1beb327a45d7`
- `processed_results/stage_a_artifact_audit.json` — SHA-256 `3f9886cd20cf44c6dc5a2b561812fb4f66cfadd03ad5703434f80379a7b92ce2`
- `raw_results/stage-a-audit-bias10-T16p587-combined-n5000000/batch_manifest.json`

The high-energy analog yield from this method audit is about 34% of the E910 high-energy central value. That is a diagnostic tension, not a completed validation result: Stage A was designed to audit bias at one energy, carries only 33 analog accepted events, and does not supply the low-energy cell or the energy ratio. Do not label FTFP_BERT validated or rejected from this observation alone.

## Provenance gaps and technical cautions

### Historical manifest drift

`config/stage_a_frozen_manifest.json` and `config/stage_a_frozen_manifest_v2.json` are preserved historical manifests with SHA-256 values:

- `ac1972dadf69a1fae642ff7ce07456067ffa8d0e70a09899d2fc9ad857a26e64`
- `a4d9545aeb8347e199f868520a18053a5e8cd19a29e97ccea9081ee8fdc65705`

The v2 manifest accurately freezes the analog-start transport source and executable. It is not a complete final inventory: it predates `combine_batches.py`, the final analyzer diagnostic fields and the batch-count metadata added to `study.json`.

The analog run recorded study hash:

`cdab315cdb402e4cb9a5130ca539d393058a6b9615d61829da3067de62973294`

The five biased batches and current `study.json` recorded:

`38f1253082c0a8089f49dc9caf435617aff3b7eb382ee053ec05235f6d5e6340`

The change added five-batch execution metadata; all resolved transport parameters, `main.cc`, bias operator and executable hashes are identical. Per-case `resolved_config.json` is the authoritative record. Do not rewrite or delete the historical manifests. A future Stage B release needs a new versioned manifest that freezes its final source, analyzer, stopping rule and exact current configuration before any event generation.

### Residual `tracking` fate records

Twelve factor-10 creation records, total weight 1.3155, retain `fate=tracking`. They were inserted when proposed as secondaries but never received `PostUserTrackingAction`. They do not appear in the first-exit or accepted numerators and do not break event/ledger weight closure. The predeclared gate still passes. Delta should inspect their Geant4 track status before Stage B and either relabel them as never-stacked/killed secondaries or explicitly exclude them from a creation-fate diagnostic. Preserve the present Stage A result unchanged.

### Stage B preparation is incomplete

Passing Stage A's computational gate does not make Stage B immediately executable. Before release, Delta/Orchestrator must:

1. record formal Stage A adjudication and Stage B release;
2. define the previously mentioned but not numerically frozen “decisive incompatibility” early-stop boundary;
3. implement and verify a Stage B combiner/analyzer for two energies, log-ratio uncertainty, absolute 95% guardrails, effective sample size and cap-limited outcomes;
4. resolve or explicitly bound the 12 `tracking` creation records;
5. create a new immutable pre-run manifest, without overwriting either historical Stage A manifest;
6. keep `FTFP_BERT` fixed and preserve the SIM008 factor-2.6 model-systematic warning.

## Reproducing the Stage A audit without running Geant4

Use the existing combined directory:

```bash
ROOT='/Users/prateek/Documents/Codex/2026-09-23/referenced-chatgpt-conversation-this-is-an-2'
SIM="$ROOT/outputs/Living Energy Research/07_simulations/SIM009"
PY='/Users/prateek/Documents/Codex/2026-09-23/referenced-chatgpt-conversation-this-is-an/work/bioenv/bin/python'

"$PY" "$SIM/model/frozen_v1/analyze_bias_audit.py" \
  --analog "$SIM/raw_results/stage-a-audit-analog-T16p587-n10000000" \
  --biased "$SIM/raw_results/stage-a-audit-bias10-T16p587-combined-n5000000" \
  --study "$SIM/config/study.json" \
  --output /tmp/sim009-stage-a-rerun.json \
  --plot /tmp/sim009-stage-a-rerun.png

cmp "$SIM/processed_results/stage_a_bias_audit.json" /tmp/sim009-stage-a-rerun.json
shasum -a 256 /tmp/sim009-stage-a-rerun.json
```

Expected JSON hash:

`6c38fede661bb846999104121e5a399be0c7cb578ca63df64dd7de1c46357188`

To independently rebuild the combined biased ledger, write to a fresh path because the combiner refuses to overwrite:

```bash
python3 "$SIM/model/frozen_v1/combine_batches.py" \
  --output /tmp/sim009-bias-combined \
  --case-id stage-a-audit-bias10-T16p587-combined-n5000000 \
  "$SIM/raw_results/stage-a-audit-bias10-T16p587-b001-n1000000" \
  "$SIM/raw_results/stage-a-audit-bias10-T16p587-b002-n1000000" \
  "$SIM/raw_results/stage-a-audit-bias10-T16p587-b003-n1000000" \
  "$SIM/raw_results/stage-a-audit-bias10-T16p587-b004-n1000000" \
  "$SIM/raw_results/stage-a-audit-bias10-T16p587-b005-n1000000"
```

To verify the installed executable and transport sources:

```bash
shasum -a 256 \
  "$ROOT/work/SIM009-build/compact_source_census" \
  "$SIM/model/frozen_v1/main.cc" \
  "$SIM/model/frozen_v1/CrossSectionBiasOperator.cc"
```

Expected hashes, in order:

```text
4eb4749d3901dae21056ff64de8341172b5f2aee3c62dc9fe5de18b6cc1e5c7d
9833ae53b0a03a67f4732b96dc61a36f00a54bbd1d536d4e28991133d8db9da6
27ef411e24763f1690df26b0447fff9e23769cb049388c0cc6b40bd766c7ecf6
```

Rebuilding the binary, if needed:

```bash
cmake -S "$SIM/model/frozen_v1" \
  -B "$ROOT/work/SIM009-build" \
  -DGeant4_DIR=/Users/prateek/geant4-v11.3.2/geant4-install/lib/cmake/Geant4
cmake --build "$ROOT/work/SIM009-build" -j4
```

A rebuild with a changed compiler/toolchain may produce a different binary hash; preserve that difference in a new manifest rather than overwriting historical provenance.

## Exact Delta restart procedure

1. **Start read-only.** Read this packet, `SIM009/README.md`, D014, D015, the commissioning handoff, `config/stage_a_gate.md`, `config/experimental_observable.md`, `processed_results/stage_a_bias_audit.json` and `processed_results/stage_a_artifact_audit.json`.
2. **Verify artifacts.** Run the no-Geant4 reproduction commands above. Confirm no active `compact_source_census` process and no `stage-b-*` directory.
3. **Adjudicate Stage A.** Submit the exact pass result and listed limitations to Notebook/Orchestrator. Request a formal Stage B release. Do not treat the old conditional authorization as an automatic restart after this transition instruction.
4. **Close method gaps before release.** Resolve the `tracking` fate diagnostic, implement the two-energy estimator, and freeze a numerical incompatibility stopping boundary.
5. **Freeze a new version.** Create a new, versioned pre-run manifest containing current `study.json`, transport source, executable, new Stage B analyzer, exact batch plan, seeds, stop rule, Geant4/data identity and storage estimate. Never reuse a case ID or overwrite an existing directory.
6. **Only after explicit release, execute the initial Stage B plan:** 5,000,000 biased primaries at 16.587 GeV and 16,000,000 at 11.397 GeV, preferably in independent 1,000,000-primary batches with unique deterministic case IDs. The historical caps are 10,000,000 high, 32,000,000 low and 42,000,000 total. Stop only under the newly frozen rule or at `N_eff >= 200` per cell.
7. **Analyze both cells together.** Report weighted absolute yields, event-level uncertainty, log energy ratio, E910 covariance approximation, creator/fate diagnostics, ESS, maximum weight, exact exposure, batch hashes, and both absolute and ratio pass/fail states. Preserve zero/count-limited outcomes.
8. **Return a structured handoff.** Notebook owns final status, evidence level and shared-state reconciliation. Passing E910 can only establish bounded adequacy for that p+Au observable; it cannot validate thick Ir, 25.08 GeV source yield, capture, cooling, storage, conversion or system efficiency.

If Stage B is later released, the existing runner syntax is:

```bash
python3 "$SIM/model/frozen_v1/prepare_case.py" \
  --executable "$ROOT/work/SIM009-build/compact_source_census" \
  --case-id '<new-unique-case-id>' \
  --energy 16.587 \
  --events 1000000 \
  --bias-factor 10 \
  --namespace sim009-stage-b-v1 \
  --execute
```

Use `--energy 11.397` for the low cell. This command is documentation only; this handoff does not authorize executing it.

## Non-negotiable preservation rules

- Keep SIM008 QGSP_BIC results and the 2.60 model spread as historical systematic evidence.
- Keep `FTFP_BERT` as the future default unless a later matched benchmark changes D014.
- Do not call the default physically validated.
- Keep the interrupted SIM008 47,110-event partial and the interrupted SIM009 monolithic bias attempt excluded and preserved.
- Never reuse case IDs, silently migrate runs or tune parameters to improve agreement.
- Do not open thick Ir, geometry, new energy, independent source evaluation, field architecture or downstream capture from SIM009.
- Do not equate importance-sampling gains with physical antiproton-production gains.
- Do not claim a microscopic ETC/hadronic correspondence.

## Transition conclusion

The completed Stage A data support one bounded numerical conclusion: factor-10 primary-inelastic occurrence bias reproduces analog antiproton creation, accepted yield and broad creation shapes within the predeclared statistical gates for 16.587 GeV p+Au under this Geant4 configuration. This validates the estimator configuration within the audited regime. It does not validate `FTFP_BERT` against E910. Stage B remains unrun and requires an explicit Delta/Orchestrator release after the unresolved method and provenance items are frozen.
