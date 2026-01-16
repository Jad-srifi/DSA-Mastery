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
