# Research State

- Current phase: `experiment_runner`
- Pipeline completed: `False`

## Previous phases

resource_finder (succeeded)

## Current phase context

- Phase: `experiment_runner`
- Status: `in_progress`
- Started: `2026-09-22T12:16:13.095295Z`
- Next steps:
  - Validate the report and experimental artifacts before finalizing.

## Workspace check

- Root: `/workspaces/tight-bounds-on-the-rainbow-connection-8c65`
- Directory usable: `True`

## Output validation

No phase output validation recorded yet.

## Agent notes

<!-- NEURICO_AGENT_NOTES_START -->
### resource_finder
<!-- NEURICO_AGENT_NOTES_START:resource_finder -->
- Phase complete (2026-09-22): created `papers/` (9 validated source PDFs plus
  47 reading chunks), `code/README.md`, `literature_review.md`, `resources.md`,
  `planning.md`, isolated `.venv`, `pyproject.toml`, and `uv.lock`.
- Decisive finding: for every fixed `d>=3`, published results give
  `rc(G(n,d))=Theta(log n)` w.h.p.; hence `ceil(n/d)+O(1)` is false. The likely
  prompt error is treating the universal `3n/(delta+1)+3` upper bound as a
  random-regular lower bound.
- Direct evidence: Frieze--Tsourakakis (2012), Dudek--Frieze--Tsourakakis
  (2015), Kamcev--Krivelevich--Sudakov (2016), and Molloy (2017), with full
  chunk-by-chunk notes in `literature_review.md`.
- The supplied arXiv IDs 1005.1665 and 1101.5428 are valid but unrelated; both
  were downloaded, read fully, and explicitly excluded.
- Search fallback: the local paper-finder service was unavailable and Semantic
  Scholar returned HTTP 429; arXiv, publisher pages, OpenAlex, and citation
  chaining supplied the evidence instead. No unresolved download corruption.
- Frozen top directions: scaling audit; tighten fixed-degree bounds toward
  diameter; separate growing-degree regimes. Rejected directions and scores are
  in `planning.md`.
- Next phase: reformulate the target as `rc=diam+O(1)` (or first
  `(1+o(1))diam`), extract quantitative losses in compatible-leaf/greedy-color
  proofs, and state explicit degree-range assumptions. Uncertainty: no forward
  citation found through 2026 resolving the `rc=diam` conjecture.
<!-- NEURICO_AGENT_NOTES_END:resource_finder -->

### experiment_runner
<!-- NEURICO_AGENT_NOTES_START:experiment_runner -->
Update this section at the end of the `experiment_runner` phase.
<!-- NEURICO_AGENT_NOTES_END:experiment_runner -->

<!-- NEURICO_AGENT_NOTES_END -->
