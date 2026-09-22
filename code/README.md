# Computational Tools

No external repository was identified as necessary or directly associated with the
core random-regular rainbow-connection papers.

## Installed local tools

- **NetworkX 3.4.2** (`.venv`): generate random regular graphs, compute diameter,
  inspect BFS neighborhoods, and validate candidate colorings.
- **pypdf 6.19.0** (`.venv`): validate and chunk the downloaded papers.
- **httpx 0.28.1** (`.venv`): query bibliographic APIs when available.

NetworkX does not provide an exact rainbow-connection-number routine. Exact tests
should encode “a rainbow path exists for every vertex pair” as SAT/ILP for a fixed
palette and increase the palette size. Because exact rainbow connection is
computationally hard, this is suitable only for small graphs and hypothesis triage.
