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
