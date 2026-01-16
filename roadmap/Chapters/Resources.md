### Operating cadence (fixed at 15h/week)
- **6h/week — Concept ingestion (active):** watch/read → write your own pseudocode + invariant → prove correctness sketch → derive complexity.
- **6h/week — Deliberate problem practice (timed):** 3–5 problems/week; each gets (a) 25–45 min cold attempt, (b) post-mortem, (c) re-solve from scratch 48–72h later.
- **3h/week — Implementation + measurement + writing:** implement from scratch, unit/property tests, microbenchmarks, one short technical note/week.

### Cumulative project (starts Week 1, evolves all year)
**Project name:** **DSA Lab** — an open-source “algorithmic toolkit + benchmarking + explainers + visualizations”.

**Product dimension**
- A reusable library/package of DS + algorithms with clean APIs.
- CI tests, property-based tests, fuzz tests, and benchmark harness.
- Optional: a small visualization module for key algorithms (sorting, BFS/DFS, Dijkstra, DP table, max-flow).

**Research dimension**
- For each major algorithm family: a short write-up with (1) model assumptions, (2) invariant/correctness proof sketch, (3) asymptotic analysis, (4) empirical validation plots/tables, (5) failure modes/adversarial cases.

**Milestones**
- **Week 1:** repo scaffolding, CI, test/bench harness, documentation templates.
- **Week 4:** proof+analysis “primer” notes + baseline benchmark methodology report.
- **Week 12:** DS module v1 (arrays→graphs) + benchmarks vs built-ins.
- **Week 24:** algorithms module v1 (sorting/greedy/DP/graph) + visualization for 2 algorithms.
- **Week 34:** advanced DS module (range structures + strings) + performance report on cache/constant factors.
- **Week 44:** flows + NP/approx module + benchmark study (Dinic vs push-relabel or variants).
- **Week 52:** final release + written “defense”: design decisions, proofs, empirical results, limitations, and one original improvement.

### Global resource library (free)
Use these repeatedly; each topic section references them by ID.

- **R1 — MIT OCW 6.006 Introduction to Algorithms (Spring 2020), 32 videos.**
- **R2 — MIT OCW 6.046J Design and Analysis of Algorithms (Spring 2015), 34 videos + problem-solving videos.**
- **R3 — MIT OCW 6.042J Mathematics for Computer Science (Spring 2015), 111 videos + free textbook PDF.**
- **R4 — Open Data Structures (Pat Morin), free HTML/PDF + code.**
- **R5 — Dasgupta–Papadimitriou–Vazirani “Algorithms” free PDF (DPV).**
- **R6 — Stanford Algorithms playlists: Algorithms 1 (75 videos) + Algorithms 2 (95 videos).**
- **R7 — Tim Roughgarden “A Second Course in Algorithms” (Stanford CS261), 21 lessons (flows/LP/approx).**
- **R8 — MIT OCW 6.851 Advanced Data Structures (Spring 2012), 22 videos.**
- **R9 — William Fiset Data Structures playlist (covers many implementation details).**
- **R10 — William Fiset Network Flow playlist (Ford–Fulkerson, Edmonds–Karp, Dinic, matching).**
- **R11 — CP-Algorithms reference (dense, implementation-oriented).**
- **R12 — USACO Guide (curated topic ladders + practice).**
- **R13 — VisuAlgo visualizations (fast intuition check).**
- **R14 — Practice platforms:** Codeforces problemset, AtCoder contests, Kattis archive.
