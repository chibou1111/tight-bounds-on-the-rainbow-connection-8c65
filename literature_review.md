# Literature Review: Rainbow Connection of Random Regular Graphs

> Created and last updated: 2026-09-22

## Review Scope

The review asks what is known about the rainbow connection number of a uniform
random `d`-regular graph, whether the proposed `ceil(n/d)+O(1)` scaling is
consistent with those results, and which probabilistic techniques could sharpen
the best valid bounds.

Papers are included when they directly treat rainbow connection of random
regular graphs, establish a prerequisite diameter/expansion result, or provide a
general bound explicitly invoked by the direct literature. Papers about different
rainbow invariants or unrelated probability models are excluded except for a
small number of contextual sources. The search covers foundational work through
2026 and uses arXiv, OpenAlex/Semantic Scholar metadata, publisher pages, and
citation chaining.

## User-Specified Resource Audit

### Mari et al., *Directly estimating non-classicality* (arXiv:1005.1665)

- Pages 1--3 (chunk 1 of 2): defines quantum non-classicality by trace distance
  from positive-Wigner-function states; uses classical/quantum Bochner theorems
  and a semidefinite program to certify lower bounds from quadrature data.
- Pages 4--5 (chunk 2 of 2): reports an optical single-photon experiment and
  histogram error analysis, then discusses extensions to entanglement witnesses.
- Screening decision: exclude. Neither graph theory, rainbow paths, random
  regular graphs, nor a transferable combinatorial lemma appears.

### Briscoe and De Wilde, *The Computing of Digital Ecosystems* (arXiv:1101.5428)

- Pages 1--3 (chunk 1 of 6): introduces bio-inspired distributed software,
  mobile multi-agent systems, and service-oriented architectures. Its use of
  “ecosystem” and network language is unrelated to edge-coloured graph paths.
- Pages 4--6 (chunk 2 of 6): surveys web-service standards and distributed
  evolutionary computing, especially coarse-grained island models.
- Pages 7--9 (chunk 3 of 6): proposes a peer-to-peer “Digital Ecosystem” whose
  software agents migrate between adaptive habitats; mentions small-world
  topology only as a systems analogy, with no rainbow-colouring result.
- Pages 10--12 (chunk 4 of 6): describes simulations of agent aggregation under
  uniform, Gaussian, and power-law user requests and evaluates fit with chi-square
  tests; this is not a random-regular-graph model.
- Pages 13--15 (chunk 5 of 6): reports modularity experiments, mixed chi-square
  goodness-of-fit outcomes, and concludes with software-architecture claims about
  self-organization and scalability.
- Pages 16--18 (chunk 6 of 6): bibliography only. No cited source concerns rainbow
  connection or random regular graph asymptotics.
- Screening decision: exclude after full-text review. The supplied arXiv identifier
  is unrelated to the research question.

## Deep-Reading Notes: Direct Random-Regular Results

### Dudek, Frieze, and Tsourakakis, *Rainbow Connection of Random Regular Graphs*

- Pages 1--3 (chunk 1 of 6): Theorem 1 states that for fixed `r >= 4`,
  `rc(G(n,r)) = O(log n)` w.h.p.; since `diam(G(n,r)) ~ log_{r-1} n`, this is
  order-tight. The proof begins with radius `k_r = log_{r-1}(K_1 log n)`,
  locally tree-like neighborhoods, and a sequential random coloring in which an
  edge avoids colors used within edge-distance `k_r`, using `q = Theta(log n)`
  colors. This explicitly identifies `3n/(delta+1)+3` as a general upper bound,
  not a lower bound.
- Pages 4--6 (chunk 2 of 6): pairs leaves of two rooted neighborhood trees so
  root-to-leaf paths have disjoint color sets, then grows/prunes larger trees and
  seeks one of many vertex-disjoint connectors. Lemmas 2--3 count compatible leaf
  pairs in two colored complete `d`-ary trees; local color separation rather than
  globally unique colors suffices.
- Pages 7--9 (chunk 3 of 6): Corollary 4 extracts a compatible matching of at
  least `d^L/10` leaves. The random graph is exposed through the configuration
  model. Lemma 5 proves small vertex sets are unicyclic at worst and only
  polylogarithmically many vertices lie near short cycles. Coloring is a random
  greedy proper coloring of the `k_r`-th power of the line graph.
- Pages 10--12 (chunk 4 of 6): paired exploration trees are grown while pruning
  collisions and color conflicts. Conditional color probabilities are bounded by
  `2/q`; Chernoff bounds preserve branching factor at least `r-1.1` until fronts
  reach polynomial size. The second tree is coupled by injections so corresponding
  root paths remain mutually rainbow.
- Pages 13--15 (chunk 5 of 6): breadth-first fronts of size `n^{3/5}` yield over
  `n^{1/21}` disjoint candidate connectors; a conditional-probability product
  shows one is rainbow w.h.p. Intersecting or unicyclic neighborhoods are handled
  by trimming/augmentation and recoloring `o(log n)` exceptional edges. The binary
  tree obstruction explains failure at `r=3`; the authors flag both the hidden
  constant and growing `r` as open technical directions.
- Pages 16--17 (chunk 6 of 6): suggests Kim--Vu random-graph sandwiching for part
  of the growing-degree problem and supplies the source chain for configuration
  models, diameter/radius bounds, sparse random graphs, and general minimum-degree
  estimates.

### Kamčev, Krivelevich, and Sudakov, *Some Remarks on Rainbow Connectivity*

- Pages 1--3 (chunk 1 of 4): Theorem 1.2 proves `rc(G(n,r)) <= c log n/log r`
  w.h.p. for every fixed `r >= 5`, matching the diameter order uniformly in `r`.
  Lemma 2.1 is the core edge-splitting principle: if two connected spanning
  subgraphs overlap in at most `c` edges, then `rc(G) <= diam(G_1)+diam(G_2)+c`.
  Theorem 1.3 extends the method to sufficiently high-degree edge expanders.
- Pages 4--6 (chunk 2 of 4): a Lovász-local-lemma splitting theorem partitions a
  sufficiently strong regular expander into two expanding spanning subgraphs.
  For random regular graphs, contiguity with edge-disjoint unions of random
  regular graphs/Hamilton cycles gives the result for `r >= 6`; the `r=5` case
  reduces to showing a cycle plus a random quarter-size matching has logarithmic
  diameter, proved via hypergeometric gap tails.
- Pages 7--9 (chunk 3 of 4): develops the distinct vertex-rainbow analogue. A
  local-lemma bipartition ensures every vertex has many neighbors in both parts;
  configuration-model density estimates then prove induced expansion and small
  diameter. This material is contextual rather than directly reusable for `rc`.
- Pages 10--11 (chunk 4 of 4): conclusion and references. The then-open cubic
  edge-rainbow case was subsequently settled by Molloy (2017); no additive-constant
  relation to `n/r` is proposed.

### Molloy, *A Note on the Rainbow Connection of Random Regular Graphs*

- Pages 1--3 (only chunk): Corollary 2 proves `rc(G(n,3)) = O(log n)` w.h.p.,
  completing all fixed degrees `r >= 3`. The new Lemma 1 handles two rooted binary
  trees whose roots have degree three: more than one third of all leaf pairs have
  color-disjoint root paths. A rearrangement/counting argument replaces the failed
  `d >= 3` tree lemma in Dudek--Frieze--Tsourakakis; their remaining probabilistic
  exploration proof then applies unchanged.

### Frieze and Tsourakakis, *Rainbow Connection of Sparse Random Graphs*

- Pages 1--3 (chunk 1 of 6): Theorem 2 gives the earlier bounds
  `O(log^4 n)` for `r=3` and `O(log^{2 theta_r} n)` for fixed `r>=4`, where
  `theta_r=log(r-1)/log(r-2)`. The common scheme is random coloring plus many
  edge-disjoint candidate paths grown from locally tree-like neighborhoods. The
  paper also proves for `G(n,p)` at the connectivity threshold that
  `rc(G) ~ max{Z_1, diam(G)}`, but that model is only contextual here.
- Pages 4--6 (chunk 2 of 6): for the binomial model, local sparsity and separation
  of low-degree vertices allow construction of paired BFS trees with many leaves
  and edge-disjoint connectors of near-diameter length. A uniform random palette
  of `(1+5 epsilon)L` colors is then analyzed through “alive” compatible leaf
  pairs.
- Pages 7--9 (chunk 3 of 6): Chernoff/product estimates preserve many compatible
  paths and handle low-degree vertices in `G(n,p)`. The random-regular proof begins:
  independent coloring fails locally, so the authors enforce different colors on
  nearby edges, use the configuration model, and grow BFS trees to polylogarithmic
  depth depending on `r`.
- Pages 10--12 (chunk 4 of 6): configuration-model sparsity guarantees at most one
  cycle in each small BFS ball and permits many disjoint half-diameter connector
  trees. The coloring is random greedy on a power of the line graph with
  `q ~ 100 log^{2 theta_r} n`. Lemma 6 uses a bipartite matching induction to pair
  `(d-1)^ell` leaves of two rainbow `d`-ary trees compatibly.
- Pages 13--15 (chunk 5 of 6): conditional probabilities under greedy coloring
  show one of `sigma` edge-disjoint candidate paths is rainbow. The cubic case
  needs depth-two induction and exceptional-cycle recoloring. The conclusion
  explicitly conjectures for random regular graphs that `rc(G)=diam(G)` w.h.p.;
  this is the literature-supported target closest to an additive bound.
- Page 16 (chunk 6 of 6): final references only.

## Key Definitions and Notation

- A path in an edge-coloured graph is **rainbow** if all its edges have distinct
  colours. A colouring is rainbow-connected if every vertex pair has a rainbow
  path. `rc(G)` is the minimum palette size of such a colouring.
- `G(n,d)` is uniform over labelled simple `d`-regular graphs on `n` vertices;
  `nd` must be even. The direct theorems below take `d` fixed while `n -> infinity`.
- An event holds **with high probability** (w.h.p.) when its probability tends to
  one along admissible `n`.
- Always `diam(G) <= rc(G) <= n-1`; the upper bound follows by colouring a
  spanning tree with distinct colours.
- The configuration model pairs `nd` half-edges uniformly. For fixed `d`, its
  probability of producing a simple graph stays bounded away from zero, so a
  w.h.p. statement in the pairing model transfers to `G(n,d)`.

## Known Results and Logical Consequences

1. **Diameter (Bollobás--Fernandez de la Vega, 1982).** For fixed `d >= 3`,
   `diam(G(n,d)) = (1+o(1)) log_{d-1} n` w.h.p. Consequently
   `rc(G(n,d)) >= (1+o(1)) log_{d-1} n`.
2. **First random-regular bound (Frieze--Tsourakakis, 2012).** For fixed `d>=4`,
   `rc=O(log^{2 theta_d} n)` with `theta_d=log(d-1)/log(d-2)`; for `d=3`,
   `rc=O(log^4 n)` w.h.p.
3. **Correct order for `d>=4` (Dudek--Frieze--Tsourakakis, 2015).** For fixed
   `d>=4`, `rc(G(n,d))=O(log n)` w.h.p.
4. **Degree-sensitive form for `d>=5` (Kamčev--Krivelevich--Sudakov, 2016).** An
   absolute `C` satisfies `rc(G(n,d)) <= C log n/log d` w.h.p. for fixed `d>=5`.
5. **Cubic completion (Molloy, 2017).** `rc(G(n,3))=O(log n)` w.h.p.

Together, results 1, 3, and 5 give, for every fixed `d>=3`,

`rc(G(n,d)) = Theta(log n)` w.h.p.

The universal minimum-degree theorem of Chandran--Das--Rajendraprasad--Varma,
`rc(G) <= 3n/(delta+1)+3`, concerns worst-case connected graphs. It supplies no
lower bound for random regular graphs. Caro et al.'s extremal examples showing the
coefficient 3 is necessary are deliberately high-diameter graphs and do not model a
typical regular expander.

## Assessment of the Stated Hypothesis

The hypothesis `rc(G)=ceil(n/d)+O(1)` is false when `d>=3` is fixed. Indeed,
`ceil(n/d)=Theta(n)`, whereas the established upper bound is `O(log n)` w.h.p.;
the two quantities differ by `Theta(n)`, not by a bounded additive term. The
claimed “known `O(log n/d)` gap” appears to conflate the general minimum-degree
upper bound with a random-regular lower bound.

If `d=d(n)` is intended to grow, the conjecture is underspecified: admissible degree
range, parity, and uniformity of error terms matter, and neither fixed-degree theorem
can simply be extrapolated. The Moore/diameter scale is roughly `log n/log(d-1)`
until the dense regime changes the diameter discretely; `n/d` is a different scale.

## Proof Techniques in the Literature

- **Local tree growth plus many routes:** expose locally tree-like BFS balls in the
  configuration model, pair compatible leaves, grow large disjoint fronts, and use
  many candidate connecting paths so one survives colour conflicts.
- **Local colour separation:** randomly greedily colour a power of the line graph.
  Every short root path is automatically rainbow, while conditional colour
  probabilities remain controlled.
- **Compatible-leaf counting:** inductive matching/counting lemmas for two rooted
  trees ensure many pairs of root paths have disjoint colour sets. Molloy's cubic
  refinement is essential at branching factor two.
- **Edge splitting:** decompose the graph into two connected spanning subgraphs,
  use disjoint palettes indexed by distance layers, and obtain
  `rc(G) <= diam(G_1)+diam(G_2)+|E_1 intersect E_2|`. Contiguity of random-regular
  decompositions and expander splitting make this especially clean for `d>=5`.
- **Exceptional-cycle repair:** local cycles are sparse; trim or recolour their
  edges with a small auxiliary palette.

## Gaps, Open Problems, and Recommended Strategy

The direct 2012 paper conjectures `rc(G(n,d))=diam(G(n,d))` w.h.p. A forward
citation search through September 2026 found no paper resolving this for fixed
random regular graphs. Thus even `rc=diam+O(1)` remains unsupported by the sources
reviewed, while the known bounds leave a constant-factor (hence additive
`Theta(log n)`) gap.

The recommended proof program is therefore:

1. Replace the false target by the explicit fixed-degree question
   `rc(G(n,d)) = diam(G(n,d))+O(1)` (or first `(1+o(1))diam(G)`).
2. Quantify constants in the locally tree-like routing proof. The main losses are
   the large safety palette, pruning from colour conflicts, and union bounds over
   all vertex pairs.
3. Investigate a hybrid of edge splitting and coupled BFS routing: splitting alone
   tends to sum two diameters, so an additive result needs paths whose two halves
   share a coordinated palette rather than disjoint full palettes.
4. Treat growing `d` as a separate theorem with explicit degree ranges; do not mix
   it into the fixed-degree statement without uniform contiguity/diameter estimates.

Small-instance computation can test revised conjectures but cannot establish the
asymptotic claim. Exact `rc` is computationally hard; a SAT/ILP feasibility model
over a fixed palette, sampled with NetworkX random regular graphs, is the most useful
computational support.

## Key Bibliography

- Frieze and Tsourakakis (2012), arXiv:1201.4603, DOI 10.37236/2784.
- Dudek, Frieze, and Tsourakakis (2015), arXiv:1311.2299,
  DOI 10.1137/140998433.
- Kamčev, Krivelevich, and Sudakov (2016), arXiv:1501.00821,
  DOI 10.1002/jgt.22003.
- Molloy (2017), DOI 10.37236/6789.
- Chandran, Das, Rajendraprasad, and Varma (2012), arXiv:1010.2296,
  DOI 10.1002/jgt.20643.
- Caro, Lev, Roditty, Tuza, and Yuster (2008), DOI 10.37236/781.
- Bollobás and Fernandez de la Vega (1982), DOI 10.1007/BF02579310.

## Search and Screening Record

The local paper-finder script was attempted first in diligent mode but its service
was unavailable. Manual searches then used arXiv, publisher pages, OpenAlex, web
search, and backward/forward citation chaining. Queries included “rainbow connection
random regular graphs,” “rainbow connectivity sparse random graphs,” “rainbow
connection connected dominating sets,” and exact-title/citation searches for the
four direct papers. Semantic Scholar's unauthenticated API returned HTTP 429, so
OpenAlex supplied citation metadata. Nine PDFs were downloaded and validated: seven
included sources and two user-specified exclusions. Four direct random-regular papers
were read in full via every generated PDF chunk; the remaining relevant papers were
screened by abstract, introduction, theorem statements, and cited use.
