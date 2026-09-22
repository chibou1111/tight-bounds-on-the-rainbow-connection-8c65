# Research Direction Triage

## Scope diagnosis

For fixed degree `d >= 3`, the stated hypothesis `rc(G) = ceil(n/d) + O(1)` is
incompatible with the established result `rc(G(n,d)) = Theta(log n)` with high
probability. The expression `3n/(delta+1)+3` occurring in the literature is a
universal **upper** bound in terms of minimum degree, not a matching lower bound.
The project should therefore begin by testing and correcting the scaling premise.

Scoring is on a 1--5 scale for (L) literature support, (H) relevance to the stated
hypothesis, (I) expected information gain, and (F) implementation feasibility.

| Rank | Direction | L | H | I | F | Total | Decision |
|---:|---|---:|---:|---:|---:|---:|---|
| 1 | Fixed-degree scaling audit: formally contrast the conjectured `n/d` scale with diameter lower bounds and known `O(log n)` rainbow colorings | 5 | 5 | 5 | 5 | 20 | Retain |
| 2 | Tighten the fixed-degree result toward the diameter: extract constants and bottlenecks from tree-growth, switching, and edge-splitting proofs | 5 | 5 | 5 | 3 | 18 | Retain |
| 3 | Degree-regime phase diagram: determine where fixed-`d` logarithmic behavior gives way to constant diameter, and formulate a corrected conjecture for growing `d=d(n)` | 4 | 4 | 5 | 3 | 16 | Retain |
| 4 | Exact small-instance computation (enumeration/optimization) to compare `rc(G)`, diameter, and `ceil(n/d)` | 3 | 4 | 4 | 4 | 15 | Prune for this phase; useful validation after the scaling correction |
| 5 | Apply the connected-dominating-set bound directly to claim `n/d+O(1)` | 4 | 3 | 2 | 5 | 14 | Reject: it is only an upper bound and has leading constant 3 in the cited theorem |
| 6 | Prove the supplied `ceil(n/d)+O(1)` formula for every fixed `d >= 3` | 1 | 5 | 1 | 1 | 8 | Reject: contradicted by known `Theta(log n)` results |
| 7 | Transfer Erdős--Rényi threshold results without conditioning on regularity | 3 | 2 | 2 | 3 | 10 | Reject: different probability model and parameter regime |
| 8 | Focus on vertex-rainbow connectivity or rainbow `k`-connectivity | 3 | 1 | 2 | 3 | 9 | Reject: distinct invariant and scope drift |

The search space is frozen to directions 1--3 unless later evidence invalidates
this ranking.
