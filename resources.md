# Resources Catalog

## Summary

Nine PDFs were downloaded: seven relevant graph-theory sources and two explicitly
supplied but unrelated arXiv papers, retained and documented for auditability. The
central conclusion is that the proposed fixed-degree hypothesis is already
contradicted by `rc(G(n,d))=Theta(log n)` w.h.p.

## Papers

| Title | Authors | Year | File | Key result/use |
|---|---|---:|---|---|
| Rainbow Connection of Random Regular Graphs | Dudek, Frieze, Tsourakakis | 2015 | `papers/1311.2299_rainbow_connection_random_regular.pdf` | `O(log n)` for fixed `d>=4` |
| Some Remarks on Rainbow Connectivity | Kamčev, Krivelevich, Sudakov | 2016 | `papers/1501.00821_some_remarks_rainbow_connectivity.pdf` | Edge splitting; `O(log n/log d)` for fixed `d>=5` |
| A Note on the Rainbow Connection of Random Regular Graphs | Molloy | 2017 | `papers/molloy_2017_note_random_regular.pdf` | `O(log n)` for `d=3` |
| Rainbow Connection of Sparse Random Graphs | Frieze, Tsourakakis | 2012 | `papers/1201.4603_rainbow_connectivity_sparse_random.pdf` | First direct bounds; conjectures `rc=diam` |
| Rainbow Connection Number and Connected Dominating Sets | Chandran et al. | 2012 | `papers/1010.2296_connected_dominating_sets.pdf` | Universal `3n/(delta+1)+3` upper bound |
| On Rainbow Connection | Caro et al. | 2008 | `papers/caro_et_al_2008_on_rainbow_connection.pdf` | Foundational extremal/minimum-degree results |
| Rainbow Connections of Graphs -- A Survey | Li, Sun | 2011 | `papers/1101.5747_rainbow_connections_survey.pdf` | Definitions and pre-2011 landscape |
| Directly Estimating Non-Classicality | Mari et al. | 2010 | `papers/1005.1665_directly_estimating_nonclassicality.pdf` | Excluded: unrelated quantum physics |
| The Computing of Digital Ecosystems | Briscoe, De Wilde | 2011 | `papers/1101.5428_computing_digital_ecosystems.pdf` | Excluded: unrelated distributed systems |

See `papers/README.md` for full metadata and `papers/pages/` for reading chunks.

## Prior Results Catalog

| Result | Source | Precise scope | Use |
|---|---|---|---|
| `diam(G)<=rc(G)` | Definition/foundational literature | Every connected graph | Fundamental lower bound |
| `diam(G(n,d))=(1+o(1))log_{d-1}n` w.h.p. | Bollobás--Fernandez de la Vega (1982), cited by all direct papers | Fixed `d>=3` | Gives logarithmic lower bound |
| `rc(G(n,d))=O(log n)` w.h.p. | Dudek et al.; Molloy | Fixed `d>=4`; fixed `d=3` | Falsifies `n/d+O(1)` for fixed `d` |
| `rc(G(n,d))<=C log n/log d` w.h.p. | Kamčev et al. | Fixed `d>=5`, absolute `C` | Correct degree-sensitive order |
| `rc(G)<=diam(G_1)+diam(G_2)+c` | Kamčev et al., Lemma 2.1 | Two connected spanning subgraphs with overlap at most `c` | Edge-splitting method |
| `rc(G)<=gamma_c(G)+2` | Chandran et al. | Connected, minimum degree at least 2 | Dominating-set transfer |
| `rc(G)<=3n/(delta+1)+3` | Chandran et al., Theorem 10 | Every connected `n`-vertex graph | Worst-case upper bound, not random lower bound |

## Computational Tools

| Tool | Purpose | Location | Notes |
|---|---|---|---|
| NetworkX 3.4.2 | Random regular samples, diameter/BFS analysis | `.venv` | Installed; no exact `rc` solver |
| pypdf 6.19.0 | PDF validation and chunking | `.venv` | Installed and used |
| httpx 0.28.1 | OpenAlex/Semantic Scholar queries | `.venv` | Semantic Scholar rate-limited; OpenAlex worked |

No repository was cloned because none was user-specified and the direct papers do
not publish a required implementation.

## Resource Gathering Notes

The prescribed paper-finder was run first in diligent mode. Its local service was
not running, so the review continued through arXiv, publisher pages, OpenAlex,
manual web search, and citation chasing. Semantic Scholar returned HTTP 429.
Selection prioritized papers directly proving random-regular bounds, then the
diameter/minimum-degree prerequisites and a survey. Forward-citation checks of the
2015--2017 core papers found no later work resolving the fixed-degree `rc=diam`
conjecture through September 2026.

The two URLs supplied in the prompt were a notable challenge: both IDs are valid
but point to unrelated fields. They were downloaded, chunked, read in full, and
excluded transparently rather than silently substituted.

## Recommendations for Proof Construction

1. **Correct the target:** study `rc(G(n,d))=diam(G(n,d))+O(1)` or first
   `rc=(1+o(1))diam`; the stated `n/d+O(1)` target is false for fixed `d`.
2. **Reuse:** configuration-model local sparsity, compatible-leaf lemmas, greedy
   coloring of powers of line graphs, and edge splitting.
3. **Main obstacle:** current proofs lose constants in palettes, pruning, and
   all-pairs union bounds; edge splitting also naturally sums two diameters.
4. **Computation:** use sampled random regular graphs plus SAT/ILP only to test
   small cases and revised conjectures, not as asymptotic evidence.
