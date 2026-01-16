## Part A: Structured text roadmap (detailed domain/subdomain explanations, time allocation, free resources, projects, reviews, mastery metrics)

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

---

## Phase 0 (Weeks 1–4, 60h): Foundations

### F1 — Tooling, language baseline, testing, benchmarking (Core)
- **Time:** 12h (~0.8w)
- **Dependencies:** none
- **What to master (atomic components)**
  - Single primary implementation language for the entire roadmap; enforce consistent style.
  - Unit testing discipline: arrange/act/assert, edge-case suites, randomized tests.
  - Property-based testing: invariants (e.g., heap property, BST ordering, DSU connectivity).
  - Benchmark hygiene: warmup, multiple trials, input generation, avoid misleading microbenchmarks.
  - Debug workflow: minimal reproducer, assertions, trace logs.
- **Free resources**
  - R1 (coding + algorithmic thinking context).
  - R4 (implementation-heavy DS examples).
- **Independent validation project**
  - Create repo skeleton: `src/`, `tests/`, `bench/`, `notes/`.
  - Implement 3 tiny reference functions (e.g., binary search, gcd, top-k via heap) with tests.
  - Benchmark harness produces a reproducible report from a single command.
  - **Completion criteria:** CI green; ≥90% line coverage on the 3 functions; benchmark report saved and versioned.
- **DSA Lab integration milestone**
  - Commit templates: “Algorithm note” (problem → invariant → proof sketch → complexity → pitfalls).
- **Meta-skills developed**
  - Experimental design (measurement discipline), communication (technical notes), abstraction (API boundaries).

### F2 — Discrete math + proof mechanics for algorithms (Core)
- **Time:** 22h (~1.5w)
- **Dependencies:** F1
- **What to master (atomic components)**
  - Logic: implication, quantifiers, contraposition; translating English constraints into predicates.
  - Proof toolkit: direct, contradiction, contrapositive, cases, induction (weak/strong), structural induction.
  - Invariants: loop invariants, data structure invariants, potential-function intuition (pre-amortized).
  - Graph math basics: paths, connectivity, DAGs, trees as graphs.
  - Counting + probability essentials used in analysis: pigeonhole, inclusion–exclusion (basic), expectation + linearity.
- **Free resources**
  - R3 (6.042 videos + free textbook PDF).
- **Independent validation project**
  - Produce a “proof portfolio” of **12** short proofs:
    - 4 induction, 4 invariants, 2 contradiction, 2 exchange-argument style.
  - **Completion criteria:** each proof includes statement, definitions, proof, and one counterexample to a nearby false statement.
- **DSA Lab integration milestone**
  - Add `notes/proofs/` with your proof portfolio; link from README.
- **Meta-skills developed**
  - Mathematical maturity, correctness reasoning, precision writing.

### F3 — Asymptotic analysis, recurrences, lower bounds (Core)
- **Time:** 14h (~0.9w)
- **Dependencies:** F2
- **What to master (atomic components)**
  - Big-O/Θ/Ω; tight bounds vs upper bounds; dominance ordering.
  - Recurrence solving: recursion tree, master theorem, substitution method, changing variables.
  - Amortized intuition (preview): aggregate analysis, potential idea (formal later).
  - Lower bounds: decision-tree lower bound for comparison sorting; adversary intuition.
  - Space complexity + hidden constants; when asymptotics lie (cache, allocation, branch predict).
- **Free resources**
  - R1 (6.006 asymptotics and analysis framing).
  - R6 (analysis modules in Stanford Algorithms 1).
  - R5 (DPV chapters on analysis and recurrences).
- **Independent validation project**
  - Solve **30** analysis exercises (functions + recurrences).
  - Build a small script that times an algorithm family over growing n and compares observed growth vs predicted Θ().
  - **Completion criteria:** 30 correct solutions + a report that includes at least 3 “prediction failed” cases and why.
- **DSA Lab integration milestone**
  - Add `notes/analysis-cheatsheet.md` with canonical growth rates and recurrence patterns.
- **Meta-skills developed**
  - Abstraction (modeling), reasoning under uncertainty (empirical vs theoretical).

### F4 — Problem framing workflow + solution write-ups (Important)
- **Time:** 6h (~0.4w)
- **Dependencies:** F1–F3
- **What to master (atomic components)**
  - Constraint-driven design: derive needed time complexity from input bounds.
  - Pattern selection: prefix sums, two pointers, hashing, BFS/DFS, DP.
  - Failure modes: off-by-one, overflow, worst-case hashing, recursion depth, graph edge cases.
  - Write-up format: statement → approach → invariant → complexity → tests.
- **Free resources**
  - R1 problem sessions + R14 practice.
- **Independent validation project**
  - Solve **12** easy problems; each must include code + invariant + complexity + tests.
  - **Completion criteria:** 12 write-ups; each has at least 5 targeted tests.
- **DSA Lab integration milestone**
  - Add `problems/` folder with the 12 write-ups as the “style standard”.
- **Meta-skills developed**
  - Communication and disciplined decomposition.

### P0R — Review & integration: Foundations consolidation (Important)
- **Time:** 6h (~0.4w)
- **Dependencies:** F1–F4
- **Review targets**
  - Re-derive from memory: big-O definitions, 5 recurrence templates, 6 proof patterns.
  - Rewrite 3 earlier solutions without looking; compare to original.
  - Convert your proofs/analysis mistakes into a “failure catalog”.
- **Restructure method**
  - Build a 1-page concept map: “problem types → invariants → canonical DS/algorithms”.
- **Independent validation project**
  - Timed mini-exam: **4** problems (1 math/proof, 1 asymptotic, 2 coding) in 2 hours.
  - **Completion criteria:** all 4 solved + post-mortem document.
- **DSA Lab milestone**
  - Tag release `v0-foundations`.

---

## Phase 1 (Weeks 5–12, 120h): Core Data Structures

### D1 — Arrays, dynamic arrays, prefix sums (Core)
- **Time:** 10h (~0.7w)
- **Dependencies:** F1–F3
- **What to master (atomic components)**
  - Dynamic array resizing: doubling strategy; amortized O(1) append.
  - Memory layout intuition: contiguous storage, cache locality.
  - Prefix sums + difference arrays: range sum queries, range updates (basic).
  - Two pointers + sliding window as array techniques.
- **Free resources**
  - R1 (dynamic arrays & DS foundations).
  - R4 (array-based structures).
- **Independent validation project**
  - Implement `DynamicArray<T>` with push/pop/insert/delete.
  - **Completion criteria:** amortized proof note + randomized test against built-in list/vector semantics.
- **DSA Lab integration milestone**
  - Add `array/` module + benchmarks showing locality benefit vs linked list for iteration.
- **Meta-skills developed**
  - Amortized reasoning, experimental validation.

### D2 — Linked lists, iterators, pointer discipline (Core)
- **Time:** 8h (~0.5w)
- **Dependencies:** D1, F1
- **What to master (atomic components)**
  - Singly vs doubly linked lists; sentinels; splice operations.
  - Iterator invalidation rules; safe deletion patterns.
  - Tradeoffs vs arrays: locality vs O(1) splicing.
- **Free resources**
  - R4 + R9 (implementation details).
- **Independent validation project**
  - Implement `SinglyList<T>` and `DoublyList<T>` with splice, reverse, cycle detection.
  - **Completion criteria:** property tests (no leaks/cycles); big-O table; microbench iteration vs array.
- **DSA Lab integration milestone**
  - Add linked list module + a note: “when linked lists are a mistake”.
- **Meta-skills developed**
  - Invariant discipline, debugging rigor.

### D3 — Stacks, queues, deques; monotonic patterns (Core)
- **Time:** 10h (~0.7w)
- **Dependencies:** D1–D2
- **What to master (atomic components)**
  - Stack/queue ADTs; array-backed ring buffer queues.
  - Deque operations and circular indexing.
  - Monotonic stack/queue patterns: next greater element, sliding window min/max.
- **Free resources**
  - R1 + R9 + R11 practice implementations.
- **Independent validation project**
  - Implement `Stack`, `Queue`, `Deque`, `MonotonicQueue`.
  - **Completion criteria:** solve 8 monotonic-stack/queue problems; each includes invariant statement.
- **DSA Lab integration milestone**
  - Add `linear-adts/` module + “pattern sheet” for monotonic structures.
- **Meta-skills developed**
  - Pattern abstraction, invariant articulation.

### D4 — Hashing and hash tables (Core)
- **Time:** 16h (~1.1w)
- **Dependencies:** D1, F3
- **What to master (atomic components)**
  - Hash function basics: uniformity goals; modular hashing pitfalls; string hashing basics.
  - Collision handling:
    - Separate chaining (lists/vectors), resizing policy.
    - Open addressing: linear/quadratic probing, double hashing, tombstones.
  - Load factor and expected time; adversarial inputs; hash flooding concept.
  - Extensions (Optional inside this subdomain): cuckoo hashing, Robin Hood hashing, Bloom filters.
- **Free resources**
  - R1 hashing lectures + R6 hashing + R4 reference.
  - R11 for implementation notes.
- **Independent validation project**
  - Implement `HashMap<K,V>` twice: chaining + open addressing.
  - **Completion criteria:** randomized differential testing vs built-in map; demonstrate performance vs load factor; include one adversarial test case.
- **DSA Lab integration milestone**
  - Add `hash/` module + benchmark report and failure analysis.
- **Meta-skills developed**
  - Probabilistic reasoning, experimental rigor.

### D5 — Heaps and priority queues (Core)
- **Time:** 12h (~0.8w)
- **Dependencies:** D1, F3
- **What to master (atomic components)**
  - Binary heap invariants; sift-up/down; heapify O(n).
  - Priority queue API; stable PQ strategies.
  - Indexed priority queue (Important): decrease-key support for Dijkstra.
  - Variants (Optional inside this subdomain): d-ary heaps, pairing heap concept.
- **Free resources**
  - R1 + R9 + R6 heap lectures.
  - R13 to sanity-check operations visually.
- **Independent validation project**
  - Implement `BinaryHeap` + `IndexedMinPQ`.
  - **Completion criteria:** property tests; heapify correctness proof sketch; use indexed PQ in Dijkstra later without modification.
- **DSA Lab integration milestone**
  - Add `heap/` module + benchmark comparisons (heapify vs repeated insert).
- **Meta-skills developed**
  - Invariant-driven coding, algorithm–DS coupling.

### D6 — Trees: representation, traversals, recursion↔iteration (Core)
- **Time:** 10h (~0.7w)
- **Dependencies:** D2, F2
- **What to master (atomic components)**
  - Binary tree representation; parent pointers; implicit trees.
  - Traversals: preorder/inorder/postorder/level-order; iterative versions with explicit stack.
  - Tree invariants; subtree aggregation concept (pre-augmentation).
- **Free resources**
  - R1 + R4 + R13.
- **Independent validation project**
  - Implement traversal library; add serializer/deserializer for binary trees.
  - **Completion criteria:** round-trip tests; iterative/recursive parity tests.
- **DSA Lab integration milestone**
  - Add `tree-core/` utilities used by later BST/balanced trees.
- **Meta-skills developed**
  - Structural induction, recursion control.

### D7 — Binary Search Trees (BST) and augmentations (Core)
- **Time:** 12h (~0.8w)
- **Dependencies:** D6, F2–F3
- **What to master (atomic components)**
  - BST invariant; search/insert/delete; deletion cases.
  - Complexity: average vs worst case; when BST degenerates.
  - Augmentations: subtree size (order statistics), subtree sum/min/max.
  - Successor/predecessor; range queries concept.
- **Free resources**
  - R1 + R9 + R6 BST content.
- **Independent validation project**
  - Implement `BSTMap<K,V>` + augmentation `subtree_size`.
  - **Completion criteria:** randomized insert/delete tests; order-statistics queries correct; include invariant check method.
- **DSA Lab integration milestone**
  - Add `bst/` module; document worst-case failure modes.
- **Meta-skills developed**
  - Correctness under mutation, invariant enforcement.

### D8 — Disjoint Set Union (Union-Find / DSU) (Core)
- **Time:** 8h (~0.5w)
- **Dependencies:** F3
- **What to master (atomic components)**
  - Set representation; union by rank/size; path compression.
  - Amortized analysis intuition (inverse Ackermann, informal ok here).
  - Applications: connectivity, Kruskal, dynamic connectivity (preview).
- **Free resources**
  - R1 + R9 DSU + R11 reference.
- **Independent validation project**
  - Implement DSU with union by size + path compression.
  - **Completion criteria:** passes randomized connectivity sequences; instrument to count parent-pointer traversals before/after compression.
- **DSA Lab integration milestone**
  - Add `dsu/` module used later in MST and clustering.
- **Meta-skills developed**
  - Amortized reasoning, instrumentation.

### D9 — Tries and prefix structures (Important)
- **Time:** 8h (~0.5w)
- **Dependencies:** D6, D1
- **What to master (atomic components)**
  - Trie node structure; terminal markers; memory tradeoffs.
  - Prefix queries; autocomplete; lexicographic traversal.
  - Variants (Optional inside this subdomain): compressed trie/radix tree; ternary search tree.
- **Free resources**
  - R4 + R11 + R13 for intuition.
- **Independent validation project**
  - Implement trie for lowercase strings with: insert, delete, prefix count, autocomplete top-k (simple heuristic).
  - **Completion criteria:** correctness tests; performance comparison vs hash set for prefix queries.
- **DSA Lab integration milestone**
  - Add `trie/` module; include memory-usage note.
- **Meta-skills developed**
  - Data modeling, memory-performance tradeoffs.

### D10 — Graph representations and core graph tooling (Core)
- **Time:** 10h (~0.7w)
- **Dependencies:** D1, D3, F2
- **What to master (atomic components)**
  - Graph models: directed/undirected, weighted/unweighted, multigraph.
  - Representations: adjacency list, adjacency matrix, edge list; conversion between them.
  - Complexity tradeoffs: dense vs sparse; memory implications.
  - Input parsing at scale; iterative traversals to avoid recursion depth issues.
- **Free resources**
  - R1 graph sections + R6 graph representations + R11.
- **Independent validation project**
  - Implement `Graph` with multiple backends + iterators for edges/neighbors.
  - **Completion criteria:** supports 10^5 edges without crashing; conversion correctness tests; benchmark adjacency list vs matrix for traversal.
- **DSA Lab integration milestone**
  - Add `graph-core/` module used by all later graph algorithms.
- **Meta-skills developed**
  - Abstraction (interfaces), algorithm engineering.

### P1R — Review & integration: Data structures synthesis (Important)
- **Time:** 16h (~1.1w)
- **Dependencies:** D1–D10
- **Review targets**
  - Implement from memory: heap, hash table, DSU (no notes), then compare.
  - Build a “DS chooser” decision chart: constraints → DS.
  - Solve 20 mixed DS problems; categorize by pattern (stack/queue/hash/tree/graph).
- **Restructure method**
  - Create a single unified invariant document: “what must always be true” per DS.
- **Independent validation project**
  - **DSA Lab DS module v1:** ship a tagged release with full tests and benchmarks.
  - **Completion criteria:** all DS pass randomized differential testing; written docs for each DS; benchmark report committed.
- **DSA Lab milestone**
  - Tag release `v1-data-structures`.

---

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

---

## Phase 3 (Weeks 25–34, 150h): Advanced Data Structures + Strings + Geometry

### X1 — Balanced search trees + augmentations (Important)
- **Time:** 24h (~1.6w)
- **Dependencies:** D7, F2–F3
- **What to master (atomic components)**
  - Rotations; height invariants.
  - AVL: balance factor; rebalancing cases.
  - Red–black trees: coloring invariants; insertion/deletion fixups (hard; do not fake it).
  - Treaps (Optional): randomized balancing via heap priority.
  - Splay trees (Optional): amortized access intuition.
  - Augmentations: order statistics, interval trees, segment-tree-like augmentation ideas.
- **Free resources**
  - R6 balanced trees segments + R9 AVL/rotations + R11 augmentation notes.
- **Independent validation project**
  - Implement **one** fully correct balanced BST (AVL or red–black) + one augmentation (subtree size).
  - **Completion criteria:** 100k randomized ops with invariant checks after each; performance comparison vs unbalanced BST.
- **DSA Lab integration milestone**
  - Add `balanced_bst/` module; include invariant-check function callable in tests.
- **Meta-skills developed**
  - Correctness under complex invariants; disciplined implementation.

### X2 — Range query data structures: Fenwick, segment tree, sparse table (Important)
- **Time:** 28h (~1.9w)
- **Dependencies:** D1, F3, X1 (optional but helpful)
- **What to master (atomic components)**
  - Fenwick tree (BIT): prefix sums; point updates; range queries via prefix differences.
  - Segment tree: build/query/update; lazy propagation for range updates.
  - Sparse table (Optional): idempotent RMQ; O(1) queries, O(n log n) preprocess.
  - Coordinate compression; offline vs online queries.
- **Free resources**
  - R9 (Fenwick, sparse table videos) + R11 (segment tree patterns) + R12 practice ladder.
- **Independent validation project**
  - Implement BIT + segment tree with lazy propagation + sparse table for RMQ.
  - **Completion criteria:** solve 20 range-query problems; include at least 5 with lazy propagation; performance report.
- **DSA Lab integration milestone**
  - Add `range_ds/` module and benchmarks for query/update regimes.
- **Meta-skills developed**
  - Abstraction (query monoids), performance engineering.

### X3 — Advanced DS concepts: persistence, rollback, amortized analysis (Optional)
- **Time:** 24h (~1.6w)
- **Dependencies:** F3, X2
- **What to master (atomic components)**
  - Persistent structures (partial persistence): persistent stack/array; persistent segment tree concept.
  - DSU with rollback (Important in competitive contexts).
  - Amortized proofs (formal): accounting and potential method; apply to dynamic arrays, splay (concept), DSU heuristics.
  - Retroactive data structures (Optional): conceptual understanding.
- **Free resources**
  - R8 (MIT 6.851 advanced DS topics) + R4 for foundational DS reasoning.
- **Independent validation project**
  - Implement DSU with rollback or persistent segment tree (choose one).
  - **Completion criteria:** solve 5 problems that require rollback/persistence; include a potential-method style amortized note for one DS.
- **DSA Lab integration milestone**
  - Add `advanced_ds/` module + one deep technical note.
- **Meta-skills developed**
  - Mathematical maturity (potential functions), design under constraints.

### X4 — String algorithms: KMP/Z, hashing, suffix structures, Aho–Corasick (Important)
- **Time:** 30h (~2.0w)
- **Dependencies:** D1, D9, F2–F3
- **What to master (atomic components)**
  - Prefix-function (KMP) and Z algorithm; pattern matching.
  - Rolling hash: collision modeling; double-hash strategy; adversarial considerations.
  - Trie-based multi-pattern matching: Aho–Corasick (Optional but high-value).
  - Suffix array + LCP; applications: longest repeated substring, unique substrings.
  - Optional: suffix automaton; suffix tree (conceptual).
- **Free resources**
  - R9 (suffix array/LCP content) + R11 string articles + R5 strings.
- **Independent validation project**
  - Implement: KMP, Z, rolling hash substring queries, suffix array + LCP; optionally Aho–Corasick.
  - **Completion criteria:** solve 15 string problems; include at least 3 where naive is O(n^2) and your solution is near-linear.
- **DSA Lab integration milestone**
  - Add `strings/` module + collision analysis note for hashing.
- **Meta-skills developed**
  - Formalization, adversarial thinking.

### X5 — Bit manipulation and bitset techniques (Optional)
- **Time:** 12h (~0.8w)
- **Dependencies:** D1, F3
- **What to master (atomic components)**
  - Bitwise ops; masks; subset iteration; popcount; lowbit tricks.
  - Bitset DP speedups; meet-in-the-middle concept.
  - Optional: XOR basis (linear basis over GF(2)).
- **Free resources**
  - R11 bit tricks + R14 practice.
- **Independent validation project**
  - Implement bitmask DP for at least one NP-ish small-n problem; implement XOR basis (optional).
  - **Completion criteria:** solve 10 bitmask/bitset problems; include one micro-optimization report (bitset vs boolean array).
- **DSA Lab integration milestone**
  - Add `bit/` utilities and a “mask iteration” template.
- **Meta-skills developed**
  - Low-level performance reasoning.

### X6 — Computational geometry basics (Optional)
- **Time:** 16h (~1.1w)
- **Dependencies:** F2–F3
- **What to master (atomic components)**
  - Orientation / cross product; segment intersection; numeric robustness.
  - Convex hull (Graham scan or monotone chain).
  - Line sweep concept (Optional): event ordering and active set idea.
- **Free resources**
  - R8 includes geometric structures topics; R11 geometry references.
- **Independent validation project**
  - Implement convex hull + segment intersection; test random point sets.
  - **Completion criteria:** passes degenerate cases (collinear points, duplicates); solves 5 geometry problems.
- **DSA Lab integration milestone**
  - Add `geometry/` module with robust orientation handling notes.
- **Meta-skills developed**
  - Mathematical modeling, numerical caution.

### P3R — Review & integration: Advanced DS synthesis (Important)
- **Time:** 16h (~1.1w)
- **Dependencies:** X1–X6
- **Review targets**
  - Implement from memory: segment tree with lazy propagation (minimal API).
  - Re-derive: KMP prefix function and suffix array construction logic (high-level).
  - Solve a mixed set: 10 range-query + 10 string problems.
- **Restructure method**
  - Build “query algebra” notes: how monoids/idempotence drive DS choice (Fenwick vs segtree vs sparse table).
- **Independent validation project**
  - **DSA Lab advanced module release:** range DS + strings integrated.
  - **Completion criteria:** stable APIs; benchmark report on at least 3 workloads; docs with invariants.
- **DSA Lab milestone**
  - Tag release `v3-advanced-ds`.

---

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

---

## Phase 5 (Weeks 45–52, 120h): Innovation & Capstone Mastery

### C1 — Research reading and replication protocol (Important)
- **Time:** 24h (~1.6w)
- **Dependencies:** all prior phases
- **What to master (atomic components)**
  - Paper reading pipeline: problem setting → model assumptions → key lemma → algorithm skeleton → proof structure → complexity.
  - Replication: implement from paper, reproduce claimed results or explain gaps.
  - Write reproducible experiments: fixed seeds, controlled input families, versioned outputs.
- **Free resources**
  - Use R8/R7 advanced material as paper-adjacent sources; use R11 to bridge implementation gaps.
- **Independent validation project**
  - Pick 1 advanced algorithm topic from your existing sources (e.g., persistent DS or flow variant) and replicate it end-to-end.
  - **Completion criteria:** “replication report” with algorithm description, proof sketch, implementation notes, and experimental results.
- **DSA Lab integration milestone**
  - Add `research/replication-1/` folder with code + report.
- **Meta-skills developed**
  - Scientific thinking, precision, defensible claims.

### C2 — High-volume problem-solving sprint with coverage guarantees (Core)
- **Time:** 40h (~2.7w)
- **Dependencies:** P4R
- **What to master (atomic components)**
  - Coverage across categories: DS, greedy, DP, graph, strings, range DS, flow, NP/approx.
  - Speed + accuracy without sacrificing proof: solve fast, then prove and test.
  - Post-mortem discipline: classify every miss into a fixable failure mode.
- **Free resources**
  - R12 topic ladders + R14 platforms (Codeforces/AtCoder/Kattis).
- **Independent validation project**
  - Solve **120** problems in 8 weeks with strict distribution:
    - 25 DP, 25 graph, 15 strings, 15 range DS, 15 greedy, 10 flow/matching, 15 mixed.
  - **Completion criteria:** ≥85% solved without editorial; every solved problem has a 5–10 line invariant/idea summary; every unsolved has post-mortem + retry.
- **DSA Lab integration milestone**
  - Add “problem index” by topic with links to your own solutions and patterns.

### C3 — Original contribution: design or improve an algorithm/DS (Core)
- **Time:** 40h (~2.7w)
- **Dependencies:** C1, C2
- **What to master (atomic components)**
  - Problem selection: constrained niche where baseline is known and measurable.
  - Novelty: new heuristic, pruning rule, augmentation, or hybrid approach.
  - Evidence: proof of correctness if exact; bound/guarantee if approximate; empirical evidence either way.
- **Free resources**
  - R7 approximation/LP framing supports “design space” thinking; R2/R8 for advanced ideas.
- **Independent validation project**
  - Deliver one of:
    - **Exact:** new DS/algorithm variant with correctness proof + complexity analysis.
    - **Approx/heuristic:** algorithm with stated objective and failure modes + measured improvement on a benchmark suite.
  - **Completion criteria:** reproducible benchmark shows ≥15% improvement in at least one meaningful metric (runtime, memory, solution quality) under clearly stated conditions; write-up includes negative results too.
- **DSA Lab integration milestone**
  - Add `original/` module + full report + experiment harness.

### C4 — Final integration: mastery defense + release (Important)
- **Time:** 16h (~1.1w)
- **Dependencies:** everything
- **What to master (atomic components)**
  - Produce a coherent “system”: DS ↔ algorithms ↔ proofs ↔ empirical validation.
  - Present your work as a consumable artifact (docs, examples, reproducible experiments).
- **Free resources**
  - R1/R2/R3 remain references for cross-checking fundamentals.
- **Independent validation project**
  - **Mastery defense bundle**
    - 25-page equivalent technical write-up (can be multiple docs).
    - 60-minute self-recorded lecture-style walkthrough (optional artifact).
    - Final library release with tagged version and changelog.
  - **Completion criteria:** run-from-scratch reproducibility; third-party can execute tests+benches with one command; documentation includes invariants and proofs for core modules.
- **DSA Lab milestone**
  - Tag release `v5-final`.

---

## Meta-skill development tracking (parallel, non-optional)
- **Abstraction:** D10 (graph interfaces), X2 (monoid thinking), C3 (designing new API + invariants).
- **Mathematical maturity:** F2/F3 baseline, A5 greedy proofs, X3 amortized, Y3 duality, Y4 reductions.
- **Reasoning (proof + invariants):** every algorithm note requires invariant + proof sketch; hardest checkpoints: X1, Y1, Y4.
- **Experimental design:** F1 benchmark hygiene → D4 hashing performance → Y5 approximation evaluation → C1 replication protocol.
- **Communication:** weekly 1-page note; phase reviews require “concept map” restructuring artifacts.

---

## Mastery criteria (explicit thresholds)

### (A) Complete comprehension + applied competence
You meet (A) only if all are true:
1. **Implementation coverage:** ≥25 data structures and ≥40 algorithms implemented from scratch with tests (property tests where applicable).
2. **Proof coverage:** ≥30 correctness proofs written (not handwavy) spanning greedy, DP, shortest paths, flow, and one NP-completeness reduction set.
3. **Problem-solving coverage:** ≥300 problems solved total, including:
   - ≥60 DP, ≥60 graph, ≥30 strings, ≥30 range DS, ≥20 flow/matching, ≥20 “hard” mixed.
4. **Performance literacy:** ≥10 benchmark reports showing predicted vs observed behavior, including at least 3 cases where constant factors/cache dominate.
5. **Reliability:** your library passes randomized stress tests for 10^5–10^6 operations on core DS without invariant violations.

### (B) Innovation / original work capability
You meet (B) only if all are true:
1. **Replication:** one end-to-end replication of an advanced algorithm/DS with reproducible experiments and a written report (C1).
2. **Original contribution:** one new algorithm/DS variant or heuristic with:
   - clear problem definition and assumptions,
   - either correctness proof (exact) or approximation/behavior claim (heuristic),
   - reproducible benchmark showing ≥15% improvement in a meaningful metric under stated conditions,
   - documented failure cases.
3. **Exposition quality:** at least 5 long-form technical notes (≥1500 words each) that a third party can follow to implement and validate the method without external materials.

---

## Part B: ASCII/Markdown hierarchical dependency tree

```text
Data Structures & Algorithms Mastery
├── Foundations
│   ├── F1 Tooling, testing, benchmarking [Core]
│   ├── F2 Discrete math + proofs [Core]
│   ├── F3 Asymptotic analysis + recurrences [Core]
│   ├── F4 Problem framing + write-ups [Important]
│   └── P0R Foundations review + integration [Important]
├── Core Data Structures
│   ├── D1 Arrays + dynamic arrays + prefix sums [Core]
│   ├── D2 Linked lists [Core]
│   ├── D3 Stacks/queues/deques + monotonic patterns [Core]
│   ├── D4 Hashing + hash tables [Core]
│   ├── D5 Heaps + (indexed) priority queues [Core]
│   ├── D6 Trees + traversals [Core]
│   ├── D7 Binary search trees + augmentations [Core]
│   ├── D8 Union-Find (DSU) [Core]
│   ├── D9 Tries + prefix structures [Important]
│   ├── D10 Graph representations + tooling [Core]
│   └── P1R DS review + integration [Important]
├── Core Algorithms & Paradigms
│   ├── A1 Sorting (comparison + non-comparison) [Core]
│   ├── A2 Searching + binary search variants + selection [Core]
│   ├── A3 Recursion + backtracking + pruning [Core]
│   ├── A4 Divide & conquer [Core]
│   ├── A5 Greedy algorithms + proof patterns [Core]
│   ├── A6 Dynamic programming (design + reconstruction) [Core]
│   ├── A7 Graph traversal + components + SCC + DAG [Core]
│   ├── A8 Shortest paths + MST [Core]
│   └── P2R Algorithms review + integration [Important]
├── Advanced Data Structures & Specialized Topics
│   ├── X1 Balanced BSTs + augmentations (AVL/RB/Treap/Splay*) [Important]
│   ├── X2 Range DS (Fenwick/Segment/Lazy/Sparse*) [Important]
│   ├── X3 Persistence + rollback + amortized proofs* [Optional]
│   ├── X4 String algorithms (KMP/Z/Hash/Suffix/Aho*) [Important]
│   ├── X5 Bit manipulation + bitset techniques* [Optional]
│   ├── X6 Computational geometry basics* [Optional]
│   └── P3R Advanced DS review + integration [Important]
├── Advanced Algorithms & Complexity
│   ├── Y1 Network flow + min-cut + min-cost* [Important]
│   ├── Y2 Matching + assignment* [Important]
│   ├── Y3 Linear programming + duality* [Optional]
│   ├── Y4 NP-completeness + reductions [Important]
│   ├── Y5 Approximation + heuristics + local search [Important]
│   ├── Y6 Beyond worst-case (randomization/cache/online*) [Optional]
│   └── P4R Advanced algorithms review + integration [Important]
└── Innovation & Capstone
    ├── C1 Research reading + replication protocol [Important]
    ├── C2 Coverage-guaranteed problem-solving sprint [Core]
    ├── C3 Original contribution (design/improve) [Core]
    └── C4 Final integration + mastery defense + release [Important]

* = includes optional subtopics inside the node as well.
