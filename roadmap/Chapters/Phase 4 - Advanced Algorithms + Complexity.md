## Phase 4 (Weeks 35–44, 150h): Advanced Algorithms + Complexity

### Y1 — Network flow and min-cut (Important)
- **Time:** 40h (~2.7w)
- **Dependencies:** D10, A7–A8, F2–F3
- **What to master (atomic components)**
  - Flow definitions, conservation, residual graphs, augmenting paths.
  - Max-flow min-cut theorem (proof sketch level).
  - Algorithms: Ford–Fulkerson, Edmonds–Karp, Dinic; complexity and practical behavior.
  - Optional: push–relabel; scaling; min-cost max-flow (often needed).
  - Modeling skill: turning problems into flow networks (the real mastery).
- **Free resources**
  - R2 (includes max-flow/min-cut lecture content) + MIT 6.046 network flow notes (extra).
  - R7 (CS261 covers flows deeply) + R10 implementation playlist.
- **Independent validation project**
  - Implement Dinic + min-cost max-flow.
  - Solve 12 flow-modeling problems (matching, circulation with demands, min-cut variants).
  - **Completion criteria:** each modeling solution includes a diagram + reduction explanation; benchmark Dinic vs Edmonds–Karp on stress graphs.
- **DSA Lab integration milestone**
  - Add `flow/` module + flow visualizer (optional) + modeling cookbook.
- **Meta-skills developed**
  - Reduction skill, algorithm engineering, proof maturity.

### Y2 — Matching and assignment (Important)
- **Time:** 20h (~1.3w)
- **Dependencies:** Y1, A7
- **What to master (atomic components)**
  - Bipartite matching: augmenting paths; relation to max-flow.
  - Hopcroft–Karp (Important).
  - Assignment problem + Hungarian algorithm (Optional but valuable).
- **Free resources**
  - R7 (matching topics) + R10 (matching via flow) + R11 references.
- **Independent validation project**
  - Implement Hopcroft–Karp and compare vs flow-based matching.
  - **Completion criteria:** solve 8 matching problems; include one assignment problem (Hungarian optional; flow formulation acceptable).
- **DSA Lab integration milestone**
  - Add `matching/` module; document when matching beats flow and why.
- **Meta-skills developed**
  - Algorithm selection and reduction literacy.

### Y3 — Linear programming basics + duality for algorithm design (Optional)
- **Time:** 16h (~1.1w)
- **Dependencies:** F2–F3, Y1 helpful
- **What to master (atomic components)**
  - LP formulation: variables, constraints, objective; feasibility vs optimization.
  - Dual LP and weak duality; intuition for primal–dual algorithms.
  - Canonical applications: max-flow/min-cut relation; set cover relaxation (concept).
- **Free resources**
  - R7 explicitly covers LP duality in algorithm design context.
- **Independent validation project**
  - Formulate 6 problems as LPs; write the dual for 3; explain dual meaning.
  - Implement one simple primal–dual approximation (e.g., vertex cover) and validate approximation ratio empirically.
  - **Completion criteria:** written derivations; working code; experiment report.
- **DSA Lab integration milestone**
  - Add `lp_notes/` and one primal–dual implementation.
- **Meta-skills developed**
  - Mathematical maturity, innovation scaffolding (design from relaxations).

### Y4 — NP-completeness, reductions, complexity basics (Important)
- **Time:** 24h (~1.6w)
- **Dependencies:** F2, A6, Y3 optional
- **What to master (atomic components)**
  - Classes: P, NP, NP-hard, NP-complete; Cook reductions.
  - Reduction mechanics: mapping instances; correctness both directions.
  - Canonical NP-complete problems: SAT/3SAT, Clique, Vertex Cover, Hamiltonian Cycle, Subset Sum/Partition.
  - What “hard” means in practice: pseudo-polynomial vs polynomial; parameter sensitivity.
- **Free resources**
  - R3 (includes halting problem exposure) + R7/R6 for NP-hard topics.
- **Independent validation project**
  - Write **10** reductions (short but correct), including at least:
    - 3SAT → VC, 3SAT → Clique, Subset Sum ↔ Partition, VC ↔ Independent Set.
  - Implement a small SAT backtracking solver for n ≤ 50 variables as a sanity tool.
  - **Completion criteria:** each reduction includes mapping + proof; SAT solver solves random small instances.
- **DSA Lab integration milestone**
  - Add `np/` notes folder with reductions and diagrams.
- **Meta-skills developed**
  - Formal reasoning, innovation axis groundwork.

### Y5 — Approximation algorithms + heuristics + local search (Important)
- **Time:** 20h (~1.3w)
- **Dependencies:** Y4, Y3 (helpful)
- **What to master (atomic components)**
  - Approximation ratio definitions; PTAS vs constant-factor.
  - Greedy approximations: vertex cover, set cover (ln n), scheduling heuristics.
  - Local search: k-exchange; when it gets stuck.
  - Empirical evaluation discipline: approximation ratio vs runtime tradeoffs.
- **Free resources**
  - R7 (approximation focus in CS261) + Roughgarden NP-hard playlist.
- **Independent validation project**
  - Implement 3 approximation/heuristic algorithms (e.g., vertex cover 2-approx, set cover greedy, TSP local search).
  - **Completion criteria:** for each, run ≥200 randomized instances; report observed quality distribution and worst cases found.
- **DSA Lab integration milestone**
  - Add `approx/` module + experiment scripts.
- **Meta-skills developed**
  - Experimental design, innovation thinking (designing under hardness).

### Y6 — Beyond worst-case: randomization, hashing theory, cache/online concepts (Optional)
- **Time:** 10h (~0.7w)
- **Dependencies:** F3, D4, A1
- **What to master (atomic components)**
  - Randomized algorithms basics: expected runtime, failure probability controls.
  - Universal hashing concept; Bloom filters (revisit).
  - Cache-oblivious idea (Optional): why asymptotics miss memory hierarchy.
  - Online/adversarial viewpoint (Optional): competitive ratio awareness.
- **Free resources**
  - R2 includes advanced topics like cryptography/cache-oblivious lectures; R6 includes randomized components.
- **Independent validation project**
  - Implement Bloom filter and evaluate false-positive rate vs theory.
  - One cache-sensitivity experiment: same Θ(n) algorithm variants with different locality.
  - **Completion criteria:** report includes predicted vs observed curves.
- **DSA Lab integration milestone**
  - Add `beyond_worst_case/` notes + experiments.
- **Meta-skills developed**
  - Probabilistic reasoning, empirical skepticism.

### P4R — Review & integration: Advanced algorithms synthesis (Important)
- **Time:** 20h (~1.3w)
- **Dependencies:** Y1–Y6
- **Review targets**
  - Re-derive max-flow min-cut theorem proof skeleton.
  - Solve 10 reductions/approx modeling exercises (not coding).
  - Implement from memory: Dinic core loop + residual update.
- **Restructure method**
  - Build “reduction atlas”: problem → known hard core → reduction pattern → approximation approach.
- **Independent validation project**
  - **DSA Lab advanced algorithms release:** flow + NP + approx integrated.
  - **Completion criteria:** one “modeling cookbook” doc; benchmarks; at least 5 fully worked flow reductions.
- **DSA Lab milestone**
  - Tag release `v4-advanced-algorithms`.
