# Scientific verification evidence and its limits

- `baseline_structural_audit.csv` / `baseline_audit_summary.json`: reproducible structural descriptors for all 60 **constructed** reference files. NOT human validation or external expert assessment.
- `INDEPENDENT_REVIEW_FORM.md`: blank future reviewer protocol. NOT evidence that the review occurred.
- `framework_tests.log`: observed local tests in this revision. Any skipped test is disclosed.
- `preflight.log`: whether required Radon/Pylint/Bandit binaries were present. This review environment has no network access to install absent dependencies.
- `python_environment.json`: current runtime package versions; NOT the archival pipeline version record.
- Original archived `evidence/` files and 210-row `outputs/metrics.csv` are preserved. Recomputed stats do not constitute a new raw metric extraction.
- `supplementary/`: exploratory post-generation checks, NOT independent prospective held-out tests.

Remaining student/external steps: original Git history; supervisor confirmation; authenticated model generation events; truly blinded external task and baseline review; full offline-container rerun with locked dependencies; signed declaration and screencast.
