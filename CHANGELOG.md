# Change Log

This file records revisions made to the artefact, together with the test runs
used to verify them.

## Status of the original development period

The submitted archive contains no version-control metadata and no change record
covering the original development period, so this file carries no entries for
that work. Nothing here has been backdated or reconstructed.

No historical Git log or supervisory timeline was included. No earlier
iteration or supervisor feedback has been retrospectively invented.

## Revisions

Each entry names the issue, the decision taken, the change made, the test
command rerun, and the observed result, so that it can be checked against the
repository history and the regenerated outputs.

| Date | Issue | Decision | Change | Test rerun | Result |
|---|---|---|---|---|---|
| 2026-10-15 | Independent-group inference on same tasks | Use paired design | Friedman, Wilcoxon, rank-biserial, Cochran Q, exact McNemar | Archived `outputs/metrics.csv` -> `src.statistics_engine.run_statistics` | Matched statistics generated; end-to-end rerun not verified |
| 2026-10-15 | Generation-visible test cases | Add separately labelled post-generation supplementary cases | `supplementary/cases.json` and `tools/run_supplementary_tests.py` | `python tools/run_supplementary_tests.py` | Completed 210/210 executions; pass-all solutions: beginner 15/30, LLM 150/150, expert 30/30; cases are post-hoc, not blind |
| 2026-10-15 | Report/provenance overclaims | Qualify statistical and reproducibility claims | README, provenance, dissertation revision | Manual consistency audit | Original generation model/date not independently authenticated |


## Verification commands

```
python -m venv .venv && .venv/bin/pip install -r requirements.txt
.venv/bin/python -m pytest tests/
.venv/bin/python run_analysis.py
```

Running the pipeline regenerates `outputs/`, `figures/` and `report/`; the raw
output of every external tool call is written to `evidence/`.

## Current review-environment verification (2026-10-15)

- Regenerated `outputs/stats.json` and `outputs/stats.md` from the unaltered metrics CSV.
- Added and executed 80 post-generation cases over 210 archived solutions;
  all runner processes returned valid results; see `supplementary/results.json`.
- Framework: 28 tests passed with the metric extractor integration test
  deselected. The integration test needs Radon/Pylint/Bandit binaries, which
  are not installed in the review environment; it has **not** passed here.
- The original Radon/Pylint/Bandit/pytest pipeline was **not** rerun end-to-end
  because dependencies are unavailable. No existing raw static evidence was
  overwritten.
- No claim of passing full CI or publishing a changed online GitHub repository.

## Further corrections performed on 2026-10-15 (current revision, not original development)

| Date | Issue | Change | Verification | Limitation |
|---|---|---|---|---|
| 2026-10-15 | Constructed-human baseline evidence overstated | Added all-60 AST structural audit, honest reviewer form and dissertation construct-validity warning | `python tools/audit_baselines.py`; 60/60 parsed, hashes stored; 30/30 framework tests not needing static tools passed | Automated descriptors do not authenticate skill labels |
| 2026-10-15 | Tool-generated report and documentation overclaim model provenance | Qualified statements in README, provenance, generated reports, dashboard, abstract and results | Cross-file terms inspected; 64-page DOCX rendered | Original provider transactions unavailable |
| 2026-10-15 | Runner might mis-score a nonzero pytest exit with a misleading passing summary | `functional_pass` now requires pytest exit code 0; nonstandard exit records reason | Framework tests and compile checks passed | No fresh all-210 archived pytest completion claimed |
| 2026-10-15 | Stale Table of Contents, figure/table pages and incomplete screencast | Refreshed displayed page references; retained student-completion marker | Rendered 64 pages for visual review | Signature, genuine screencast, original supervisory commits still absent |
| 2026-10-15 | Full static rerun not independently executable in current environment | Added a full environment manifest and explicit preflight evidence | `python run_analysis.py --skip-figures --skip-report` exited 3, identifying missing Radon/Pylint/Bandit | Full end-to-end pipeline remains unverified |

Imported-archive comparison commits, if present, are newly created change-audit commits **not** historic student development commits.
