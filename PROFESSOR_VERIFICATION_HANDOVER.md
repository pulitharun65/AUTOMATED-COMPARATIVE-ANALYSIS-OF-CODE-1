# THARUN — professor-level corrective verification handover

**Review date:** 16 October 2026  
**Scope:** Four concerns raised for Tharun Puli's MSc Cyber Security comparative-code-analysis dissertation.  
**Starting artifact:** `Tharun_Updated.zip` (provided in this conversation).  
**Important:** This revision is not certification of a 90+ mark and does not assert work performed by independent humans.

## Verified now (not hypothetical)

1. Archived benchmark remains unchanged: 30 tasks, 210 original solution records and the previously archived static evidence. Candidate and task source Python files were compared byte-for-byte with the input ZIP; **zero changes**.
2. Executed **50 eligible framework tests successfully** (one static-tool integration test excluded). When all **51** tests were run, the static extraction integration test failed because Radon/Pylint/Bandit are not installed in this environment. See `verification/professor_audit/framework_eligible_49.log` and `framework_full_50.log`.
3. Independently recomputed archived Friedman omnibus statistics using SciPy directly on archived `outputs/metrics.csv`. The five checked values match `outputs/stats.json` within tolerance. See `verification/archived_scientific_crosscheck.json`. **This is archived-data cross-checking, not a new static-analysis run.**
4. Attempted dependency installation; offline package index prevented Radon installation. See `verification/professor_audit/static_tools_install_attempt.log`.
5. Checked reviewer/test-author folders; **no authentic completed external reviewer ratings or frozen external test package exist in the supplied archive**. Historic student Git/supervision evidence and model-generation provider receipts likewise remain unauthenticated.

## Corrections made in this version

- Added `tools/archive_scientific_crosscheck.py` with mismatch detection against archived statistics; included real negative tests that detect altered saved statistics.
- Hardened `tools/windows_review_summary.py` to flag numeric static-metric drift by field/solution. The Windows summary contains `static_metric_drift_count`, examples and `requires_dissertation_reconciliation`. Static drift is not silently accepted as identical research evidence.
- Strengthened `RUN_WINDOWS_AND_SAVE.ps1`: Python 3.11 is required; archived and fresh statistics are independently crosschecked in separate evidence files; **all run outputs remain inside** `Project_Files/verification/windows_runs/`.
- Updated `.github/workflows/independent-full-verification.yml` to independently check the archived and freshly regenerated statistical results and preserve audit files.
- Hardened `tools/evidence_completion_status.py` so an arbitrary `WINDOWS_STATUS.json` with `status=PASS` does not count as a verified full run; required step exits and a passing comparison report must exist.
- Extended Git iteration inventory with actual changed-file paths from Git object history while explicitly *not* authenticating original student history.
- Validated reviewer attestation timestamps and excluded obvious placeholder entries; validated external-test freeze timestamp, rejecting future or unzoned dates. This is syntactic validation, not identity or ethics approval.
- Added new regression tests in `tests/test_professor_acceptance.py`.

## The four concerns — completion criteria

### A. Complete fresh Radon/Pylint/Bandit run (**not yet completed**)

Use a **disposable, network-restricted Windows VM or appropriate sandbox**, not an administrator session on a personal machine. The benchmark runs locally stored Python code, which is not an OS security sandbox. Install Python 3.11. Extract this ZIP and open `Project_Files`, then inspect/double-click `START_WINDOWS_RUN.cmd`.

The runner creates a separate workspace and returns a dated ZIP under:

`Project_Files/verification/windows_runs/RESULTS_<run_id>.zip`

Check the run's `WINDOWS_STATUS.json`, `windows_review_summary.json`, `fresh_stats_independent_check.json`, dependency versions, `11_complete_analysis.log`, and regenerated `outputs/`, `figures/`, `report/`, `evidence/`. A `PASS` certifies technical reproduction of that local run **only**; it does not authenticate independent reviewers or original LLM identity. If metric drift is reported, reconcile exact changes and revisions to dissertation figures before submission. Save both failed and successful results.

Alternative: push authorised project files to the genuine repository and run `.github/workflows/independent-full-verification.yml` using GitHub Actions. Record the workflow URL and commit SHA; adding a workflow without running it is not evidence.

### B. Independent baseline review (**not yet completed**)

Obtain institutional/supervisor approval as applicable, then send only the anonymous `verification/independent_review_preparation/REVIEWER_PACKET` to two genuine qualified independent assessors. NEVER send `PRIVATE_KEY_DO_NOT_SEND_TO_RATERS.csv`. Collect original dated files and attestations into `verification/external_results/reviewer_01/` and `reviewer_02/`. Run `python tools/external_evidence_review.py`. Report agreement and disagreements honestly; these reviews evaluate *constructed style labels*, not actual novice/expert human participants. The software cannot authenticate a signature or professional qualification.

### C. Independently authored specification-only tests (**not yet completed**)

Give an independent test author ONLY `verification/external_test_author_packet.zip`, without solution files or past test cases. Collect `cases.json` for all 30 tasks and `frozen_manifest.json` with valid UTC date, original SHA-256 checksum and truthful attestation. Preserve original submitted files. Run `python tools/run_external_validation.py` for format/hash checks, then `python tools/run_external_validation.py --execute` **only in an isolated, network-disabled VM**. Archive results. Because these cases post-date the original generations, describe them as *post-generation externally authored validation*, not prospective blind-generation evidence.

### D. Iteration/redesign traceability (**partially complete; earlier history unknown**)

Retain the supplied Git history, original supervision feedback and genuine existing test logs. Obtain earlier student-version Git histories, backups or supervision records **only if they actually exist**. Run `python tools/iteration_evidence_audit.py`, then write evidence-supported entries mapping dated issue → genuine code diff → real retest → observed outcome into Appendix B.3. The current commits are review-period corrections and **do not prove earlier student development work**. Do not change author dates, invent earlier commits or present Git metadata alone as independent authentication.

## What to send back for strict reassessment

Return the complete `RESULTS_<run_id>.zip` from a real successful Windows/CI run, genuine external reviewer forms/attestations, externally authored frozen tests with their execution outputs, genuine earlier development records if available, and the current dissertation. Keep the original archive and failures. A revised dissertation and score must be based only on those observed results.
