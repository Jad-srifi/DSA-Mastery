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
