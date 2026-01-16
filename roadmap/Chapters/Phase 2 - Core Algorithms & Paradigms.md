## Phase 2 (Weeks 13–24, 180h): Core Algorithms & Paradigms

### A1 — Sorting: comparison + non-comparison (Core)
- **Time:** 20h (~1.3w)
- **Dependencies:** D1, D5, F3
- **What to master (atomic components)**
  - Comparison sorts: insertion/selection, merge, quick, heap; stability; in-place vs extra memory.
  - Partition schemes; pivot strategies; worst-case quicksort.
  - Non-comparison: counting sort, radix sort (LSD/MSD) under constraints.
  - Lower bound: Ω(n log n) comparisons; when it applies.
- **Free resources**
  - R1 sorting lectures + R6 quicksort/mergesort + R5 sorting chapter.
  - R13 to validate intuition.
- **Independent validation project**
  - Implement 6 sorts + a benchmark harness and adversarial inputs.
  - **Completion criteria:** stability tests; worst-case quicksort demonstration; report on when radix wins.
- **DSA Lab integration milestone**
  - Add `sorting/` module + visualizer for 2 sorts (optional but measurable).
- **Meta-skills developed**
  - Lower-bound reasoning, empirical validation.

### A2 — Searching, binary search mastery, selection (Core)
- **Time:** 12h (~0.8w)
- **Dependencies:** D1, F3
- **What to master (atomic components)**
  - Binary search variants: first true/last true, lower_bound/upper_bound, search on answer.
  - Selection: quickselect; deterministic median-of-medians (Important).
  - Pitfalls: overflow in mid, infinite loops, invariants.
- **Free resources**
  - R1 + R6 selection content + R11 for patterns.
- **Independent validation project**
  - Implement a “binary search cookbook” with 8 templates + tests.
  - Implement quickselect + deterministic select.
  - **Completion criteria:** solve 15 “search on answer” problems; every solution states the monotonic predicate explicitly.
- **DSA Lab integration milestone**
  - Add `searching/` templates with invariant assertions.
- **Meta-skills developed**
  - Predicate thinking, invariant precision.

### A3 — Recursion, backtracking, pruning (Core)
- **Time:** 16h (~1.1w)
- **Dependencies:** F2, D3, D6
- **What to master (atomic components)**
  - Recursion trees; base cases; stack depth control.
  - Backtracking framework: choose → explore → unchoose.
  - Pruning: constraints propagation, bounding, symmetry breaking.
  - Iterative simulation with explicit stack when needed.
- **Free resources**
  - R1 + R5 recursion/DP framing + R14 practice.
- **Independent validation project**
  - Implement N-Queens + Sudoku solver + subset generation; include pruning heuristics.
  - **Completion criteria:** runtime improvement demonstrated (with/without pruning); write-up explains pruning correctness.
- **DSA Lab integration milestone**
  - Add `backtracking/` module + a small search visualizer (optional).
- **Meta-skills developed**
  - Search-space modeling, proof of pruning safety.

### A4 — Divide & conquer paradigms (Core)
- **Time:** 16h (~1.1w)
- **Dependencies:** F3, A3
- **What to master (atomic components)**
  - D&C skeleton: split → solve → combine; recurrence derivation.
  - Classic problems: inversions count, closest pair (Optional), Karatsuba/Strassen (Optional).
  - Master theorem boundaries; when it doesn’t apply.
- **Free resources**
  - R2 divide-and-conquer lectures + R6 D&C content + R5.
- **Independent validation project**
  - Implement inversion counting and at least one “non-trivial combine” algorithm.
  - **Completion criteria:** recurrence derived and solved; correctness proof includes combine-step invariant.
- **DSA Lab integration milestone**
  - Add `divide_conquer/` module and recurrence notes.
- **Meta-skills developed**
  - Recurrence modeling, compositional proofs.

### A5 — Greedy algorithms + proof patterns (Core)
- **Time:** 20h (~1.3w)
- **Dependencies:** F2–F3, D5
- **What to master (atomic components)**
  - Greedy-choice property and optimal substructure (without confusing them).
  - Proof patterns: exchange argument, cut property, matroid intuition (Optional depth).
  - Canonical problems: interval scheduling, Huffman coding, MST (Prim/Kruskal correctness).
- **Free resources**
  - R2 greedy lectures + R6 greedy playlist segments + R5.
- **Independent validation project**
  - Implement: interval scheduling, Huffman coding, MST (Kruskal + Prim).
  - **Completion criteria:** each has a written correctness proof (exchange or cut argument) and complexity analysis.
- **DSA Lab integration milestone**
  - Add `greedy/` module with proof notes and counterexamples to “tempting wrong greedies”.
- **Meta-skills developed**
  - Proof craft, “why greedy works” discipline.

### A6 — Dynamic programming (DP): state design → optimization (Core)
- **Time:** 40h (~2.7w)
- **Dependencies:** A3, F2–F3
- **What to master (atomic components)**
  - DP design workflow: define state, transitions, base cases, order, reconstruction.
  - 1D DP: fib variants, house robber, LIS (O(n^2) then O(n log n) concept).
  - 2D DP: edit distance, LCS, knapsack, grid paths.
  - Graph DP: DAG DP, tree DP basics.
  - Memoization vs tabulation; complexity by counting states/transitions.
  - Common failure: hidden exponential via huge state space.
- **Free resources**
  - R2 + R6 (Algorithms Illuminated Part 3 DP) + R5 DP chapters + R12 curated practice.
- **Independent validation project**
  - Implement **12** canonical DPs with reconstruction; include at least:
    - knapsack, edit distance, LIS, interval DP, tree DP, bitmask DP (small).
  - **Completion criteria:** each DP has a state definition + transition proof; solve 25 DP problems across difficulties.
- **DSA Lab integration milestone**
  - Add `dp/` module + DP-table visualizer for one 2D DP.
- **Meta-skills developed**
  - Abstraction (state compression), reasoning (optimal substructure), communication (state definitions).

### A7 — Graph traversal, components, DAG algorithms (Core)
- **Time:** 28h (~1.9w)
- **Dependencies:** D10, D3, F2–F3
- **What to master (atomic components)**
  - BFS/DFS; iterative DFS to avoid recursion limits.
  - Topological sort; DAG DP entry points.
  - Connected components (undirected); bipartite check.
  - Strongly connected components (Kosaraju/Tarjan); condensation DAG.
  - Bridges + articulation points (Important).
- **Free resources**
  - R1 graph algorithms + R6 SCC/toposort + R11 implementation notes + R12 ladder.
- **Independent validation project**
  - Implement BFS, DFS, topo sort, SCC, bridges/articulation.
  - **Completion criteria:** verify on random graphs + known corner cases; include a generator for adversarial graphs (deep chains, dense subgraphs).
- **DSA Lab integration milestone**
  - Add `graph_algorithms/` core traversal suite.
- **Meta-skills developed**
  - Invariant reasoning on graphs, robustness to edge cases.

### A8 — Shortest paths + MST + union-find applications (Core)
- **Time:** 20h (~1.3w)
- **Dependencies:** D5, D8, D10, A7
- **What to master (atomic components)**
  - Dijkstra (nonnegative weights) with indexed PQ; correctness proof via greedy invariant.
  - Bellman–Ford (negative edges), negative cycle detection.
  - Floyd–Warshall (all-pairs) and its DP interpretation.
  - MST: Kruskal (DSU), Prim (PQ), cut property.
  - Optional extensions: Johnson’s algorithm, 0–1 BFS, SPFA pitfalls.
- **Free resources**
  - R1 + R6 shortest paths + R11 reference.
- **Independent validation project**
  - Implement: Dijkstra (with decrease-key), Bellman–Ford, Floyd–Warshall, Kruskal, Prim.
  - **Completion criteria:** correctness proof sketches for Dijkstra + Kruskal; benchmark Dijkstra variants (binary heap vs indexed PQ).
- **DSA Lab integration milestone**
  - Add `shortest_paths/` + `mst/` modules; add visualization for BFS vs Dijkstra on same graph.
- **Meta-skills developed**
  - Algorithm-DS integration, proof discipline.

### P2R — Review & integration: Core algorithms consolidation (Important)
- **Time:** 8h (~0.5w)
- **Dependencies:** A1–A8
- **Review targets**
  - Re-solve from memory: one DP, one graph shortest-path, one greedy proof.
  - Build a “paradigm classifier”: for any new problem, map to D&C/greedy/DP/graph search.
- **Restructure method**
  - Create a single page: “common invariants by paradigm” (DP recurrence invariant, greedy cut/exchange, graph visitation invariant).
- **Independent validation project**
  - **Algorithm library v1:** integrate all implementations into stable APIs.
  - **Completion criteria:** 60-problem mixed set solved; ≥80% solved without looking up solutions; every miss has a documented failure reason.
- **DSA Lab milestone**
  - Tag release `v2-core-algorithms`.
