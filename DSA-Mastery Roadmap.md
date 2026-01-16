Part A: Structured text roadmap
Operating cadence (fixed at 15h/week)
•	6h/week — Concept ingestion (active): watch/read → write your own pseudocode + invariant → prove correctness sketch → derive complexity.
•	6h/week — Deliberate problem practice (timed): 3–5 problems/week; each gets (a) 25–45 min cold attempt, (b) post-mortem, (c) re-solve from scratch 48–72h later.
•	3h/week — Implementation + measurement + writing: implement from scratch, unit/property tests, microbenchmarks, one short technical note/week.
Cumulative project (starts Week 1, evolves all year)
Project name: DSA Lab — an open-source “algorithmic toolkit + benchmarking + explainers + visualizations”.
Product dimension
•	A reusable library/package of DS + algorithms with clean APIs.
•	CI tests, property-based tests, fuzz tests, and benchmark harness.
•	Optional: a small visualization module for key algorithms (sorting, BFS/DFS, Dijkstra, DP table, max-flow).
Research dimension
•	For each major algorithm family: a short write-up with (1) model assumptions, (2) invariant/correctness proof sketch, (3) asymptotic analysis, (4) empirical validation plots/tables, (5) failure modes/adversarial cases.
Milestones
•	Week 1: repo scaffolding, CI, test/bench harness, documentation templates.
•	Week 4: proof+analysis “primer” notes + baseline benchmark methodology report.
•	Week 12: DS module v1 (arrays→graphs) + benchmarks vs built-ins.
•	Week 24: algorithms module v1 (sorting/greedy/DP/graph) + visualization for 2 algorithms.
•	Week 34: advanced DS module (range structures + strings) + performance report on cache/constant factors.
•	Week 44: flows + NP/approx module + benchmark study (Dinic vs push-relabel or variants).
•	Week 52: final release + written “defense”: design decisions, proofs, empirical results, limitations, and one original improvement.
Global resource library (free)
Use these repeatedly; each topic section references them by ID.
•	R1 — MIT OCW 6.006 Introduction to Algorithms (Spring 2020), 32 videos. (YouTube)
•	R2 — MIT OCW 6.046J Design and Analysis of Algorithms (Spring 2015), 34 videos + problem-solving videos. (YouTube)
•	R3 — MIT OCW 6.042J Mathematics for Computer Science (Spring 2015), 111 videos + free textbook PDF. (YouTube)
•	R4 — Open Data Structures (Pat Morin), free HTML/PDF + code. (opendatastructures.org)
•	R5 — Dasgupta–Papadimitriou–Vazirani “Algorithms” free PDF (DPV). (algorithmics.lsi.upc.edu)
•	R6 — Stanford Algorithms playlists: Algorithms 1 (75 videos) + Algorithms 2 (95 videos). (YouTube)
•	R7 — Tim Roughgarden “A Second Course in Algorithms” (Stanford CS261), 21 lessons (flows/LP/approx). (YouTube)
•	R8 — MIT OCW 6.851 Advanced Data Structures (Spring 2012), 22 videos. (YouTube)
•	R9 — William Fiset Data Structures playlist (covers many implementation details). (YouTube)
•	R10 — William Fiset Network Flow playlist (Ford–Fulkerson, Edmonds–Karp, Dinic, matching). (YouTube)
•	R11 — CP-Algorithms reference (dense, implementation-oriented). (CP Algorithms)
•	R12 — USACO Guide (curated topic ladders + practice). (USACO Guide)
•	R13 — VisuAlgo visualizations (fast intuition check). (visualgo.net)
•	R14 — Practice platforms: Codeforces problemset, AtCoder contests, Kattis archive. (Codeforces)
________________________________________
Phase 0 (Weeks 1–4, 60h): Foundations
F1 — Tooling, language baseline, testing, benchmarking (Core)
•	Time: 12h (~0.8w)
•	Dependencies: none
•	What to master (atomic components)
o	Single primary implementation language for the entire roadmap; enforce consistent style.
o	Unit testing discipline: arrange/act/assert, edge-case suites, randomized tests.
o	Property-based testing: invariants (e.g., heap property, BST ordering, DSU connectivity).
o	Benchmark hygiene: warmup, multiple trials, input generation, avoid misleading microbenchmarks.
o	Debug workflow: minimal reproducer, assertions, trace logs.
•	Free resources
o	R1 (coding + algorithmic thinking context). (MIT OpenCourseWare)
o	R4 (implementation-heavy DS examples). (opendatastructures.org)
•	Independent validation project
o	Create repo skeleton: src/, tests/, bench/, notes/.
o	Implement 3 tiny reference functions (e.g., binary search, gcd, top-k via heap) with tests.
o	Benchmark harness produces a reproducible report from a single command.
o	Completion criteria: CI green; ≥90% line coverage on the 3 functions; benchmark report saved and versioned.
•	DSA Lab integration milestone
o	Commit templates: “Algorithm note” (problem → invariant → proof sketch → complexity → pitfalls).
•	Meta-skills developed
o	Experimental design (measurement discipline), communication (technical notes), abstraction (API boundaries).
F2 — Discrete math + proof mechanics for algorithms (Core)
•	Time: 22h (~1.5w)
•	Dependencies: F1
•	What to master (atomic components)
o	Logic: implication, quantifiers, contraposition; translating English constraints into predicates.
o	Proof toolkit: direct, contradiction, contrapositive, cases, induction (weak/strong), structural induction.
o	Invariants: loop invariants, data structure invariants, potential-function intuition (pre-amortized).
o	Graph math basics: paths, connectivity, DAGs, trees as graphs.
o	Counting + probability essentials used in analysis: pigeonhole, inclusion–exclusion (basic), expectation + linearity.
•	Free resources
o	R3 (6.042 videos + free textbook PDF). (YouTube)
•	Independent validation project
o	Produce a “proof portfolio” of 12 short proofs:
	4 induction, 4 invariants, 2 contradiction, 2 exchange-argument style.
o	Completion criteria: each proof includes statement, definitions, proof, and one counterexample to a nearby false statement.
•	DSA Lab integration milestone
o	Add notes/proofs/ with your proof portfolio; link from README.
•	Meta-skills developed
o	Mathematical maturity, correctness reasoning, precision writing.
F3 — Asymptotic analysis, recurrences, lower bounds (Core)
•	Time: 14h (~0.9w)
•	Dependencies: F2
•	What to master (atomic components)
o	Big-O/Θ/Ω; tight bounds vs upper bounds; dominance ordering.
o	Recurrence solving: recursion tree, master theorem, substitution method, changing variables.
o	Amortized intuition (preview): aggregate analysis, potential idea (formal later).
o	Lower bounds: decision-tree lower bound for comparison sorting; adversary intuition.
o	Space complexity + hidden constants; when asymptotics lie (cache, allocation, branch predict).
•	Free resources
o	R1 (6.006 asymptotics and analysis framing). (MIT OpenCourseWare)
o	R6 (analysis modules in Stanford Algorithms 1). (YouTube)
o	R5 (DPV chapters on analysis and recurrences). (algorithmics.lsi.upc.edu)
•	Independent validation project
o	Solve 30 analysis exercises (functions + recurrences).
o	Build a small script that times an algorithm family over growing n and compares observed growth vs predicted Θ().
o	Completion criteria: 30 correct solutions + a report that includes at least 3 “prediction failed” cases and why.
•	DSA Lab integration milestone
o	Add notes/analysis-cheatsheet.md with canonical growth rates and recurrence patterns.
•	Meta-skills developed
o	Abstraction (modeling), reasoning under uncertainty (empirical vs theoretical).
F4 — Problem framing workflow + solution write-ups (Important)
•	Time: 6h (~0.4w)
•	Dependencies: F1–F3
•	What to master (atomic components)
o	Constraint-driven design: derive needed time complexity from input bounds.
o	Pattern selection: prefix sums, two pointers, hashing, BFS/DFS, DP.
o	Failure modes: off-by-one, overflow, worst-case hashing, recursion depth, graph edge cases.
o	Write-up format: statement → approach → invariant → complexity → tests.
•	Free resources
o	R1 problem sessions + R14 practice. (YouTube)
•	Independent validation project
o	Solve 12 easy problems; each must include code + invariant + complexity + tests.
o	Completion criteria: 12 write-ups; each has at least 5 targeted tests.
•	DSA Lab integration milestone
o	Add problems/ folder with the 12 write-ups as the “style standard”.
•	Meta-skills developed
o	Communication and disciplined decomposition.
P0R — Review & integration: Foundations consolidation (Important)
•	Time: 6h (~0.4w)
•	Dependencies: F1–F4
•	Review targets
o	Re-derive from memory: big-O definitions, 5 recurrence templates, 6 proof patterns.
o	Rewrite 3 earlier solutions without looking; compare to original.
o	Convert your proofs/analysis mistakes into a “failure catalog”.
•	Restructure method
o	Build a 1-page concept map: “problem types → invariants → canonical DS/algorithms”.
•	Independent validation project
o	Timed mini-exam: 4 problems (1 math/proof, 1 asymptotic, 2 coding) in 2 hours.
o	Completion criteria: all 4 solved + post-mortem document.
•	DSA Lab milestone
o	Tag release v0-foundations.
________________________________________
Phase 1 (Weeks 5–12, 120h): Core Data Structures
D1 — Arrays, dynamic arrays, prefix sums (Core)
•	Time: 10h (~0.7w)
•	Dependencies: F1–F3
•	What to master (atomic components)
o	Dynamic array resizing: doubling strategy; amortized O(1) append.
o	Memory layout intuition: contiguous storage, cache locality.
o	Prefix sums + difference arrays: range sum queries, range updates (basic).
o	Two pointers + sliding window as array techniques.
•	Free resources
o	R1 (dynamic arrays & DS foundations). (MIT OpenCourseWare)
o	R4 (array-based structures). (opendatastructures.org)
•	Independent validation project
o	Implement DynamicArray<T> with push/pop/insert/delete.
o	Completion criteria: amortized proof note + randomized test against built-in list/vector semantics.
•	DSA Lab integration milestone
o	Add array/ module + benchmarks showing locality benefit vs linked list for iteration.
•	Meta-skills developed
o	Amortized reasoning, experimental validation.
D2 — Linked lists, iterators, pointer discipline (Core)
•	Time: 8h (~0.5w)
•	Dependencies: D1, F1
•	What to master (atomic components)
o	Singly vs doubly linked lists; sentinels; splice operations.
o	Iterator invalidation rules; safe deletion patterns.
o	Tradeoffs vs arrays: locality vs O(1) splicing.
•	Free resources
o	R4 + R9 (implementation details). (opendatastructures.org)
•	Independent validation project
o	Implement SinglyList<T> and DoublyList<T> with splice, reverse, cycle detection.
o	Completion criteria: property tests (no leaks/cycles); big-O table; microbench iteration vs array.
•	DSA Lab integration milestone
o	Add linked list module + a note: “when linked lists are a mistake”.
•	Meta-skills developed
o	Invariant discipline, debugging rigor.
D3 — Stacks, queues, deques; monotonic patterns (Core)
•	Time: 10h (~0.7w)
•	Dependencies: D1–D2
•	What to master (atomic components)
o	Stack/queue ADTs; array-backed ring buffer queues.
o	Deque operations and circular indexing.
o	Monotonic stack/queue patterns: next greater element, sliding window min/max.
•	Free resources
o	R1 + R9 + R11 practice implementations. (MIT OpenCourseWare)
•	Independent validation project
o	Implement Stack, Queue, Deque, MonotonicQueue.
o	Completion criteria: solve 8 monotonic-stack/queue problems; each includes invariant statement.
•	DSA Lab integration milestone
o	Add linear-adts/ module + “pattern sheet” for monotonic structures.
•	Meta-skills developed
o	Pattern abstraction, invariant articulation.
D4 — Hashing and hash tables (Core)
•	Time: 16h (~1.1w)
•	Dependencies: D1, F3
•	What to master (atomic components)
o	Hash function basics: uniformity goals; modular hashing pitfalls; string hashing basics.
o	Collision handling:
	Separate chaining (lists/vectors), resizing policy.
	Open addressing: linear/quadratic probing, double hashing, tombstones.
o	Load factor and expected time; adversarial inputs; hash flooding concept.
o	Extensions (Optional inside this subdomain): cuckoo hashing, Robin Hood hashing, Bloom filters.
•	Free resources
o	R1 hashing lectures + R6 hashing + R4 reference. (MIT OpenCourseWare)
o	R11 for implementation notes. (CP Algorithms)
•	Independent validation project
o	Implement HashMap<K,V> twice: chaining + open addressing.
o	Completion criteria: randomized differential testing vs built-in map; demonstrate performance vs load factor; include one adversarial test case.
•	DSA Lab integration milestone
o	Add hash/ module + benchmark report and failure analysis.
•	Meta-skills developed
o	Probabilistic reasoning, experimental rigor.
D5 — Heaps and priority queues (Core)
•	Time: 12h (~0.8w)
•	Dependencies: D1, F3
•	What to master (atomic components)
o	Binary heap invariants; sift-up/down; heapify O(n).
o	Priority queue API; stable PQ strategies.
o	Indexed priority queue (Important): decrease-key support for Dijkstra.
o	Variants (Optional inside this subdomain): d-ary heaps, pairing heap concept.
•	Free resources
o	R1 + R9 + R6 heap lectures. (MIT OpenCourseWare)
o	R13 to sanity-check operations visually. (visualgo.net)
•	Independent validation project
o	Implement BinaryHeap + IndexedMinPQ.
o	Completion criteria: property tests; heapify correctness proof sketch; use indexed PQ in Dijkstra later without modification.
•	DSA Lab integration milestone
o	Add heap/ module + benchmark comparisons (heapify vs repeated insert).
•	Meta-skills developed
o	Invariant-driven coding, algorithm–DS coupling.
D6 — Trees: representation, traversals, recursion↔iteration (Core)
•	Time: 10h (~0.7w)
•	Dependencies: D2, F2
•	What to master (atomic components)
o	Binary tree representation; parent pointers; implicit trees.
o	Traversals: preorder/inorder/postorder/level-order; iterative versions with explicit stack.
o	Tree invariants; subtree aggregation concept (pre-augmentation).
•	Free resources
o	R1 + R4 + R13. (MIT OpenCourseWare)
•	Independent validation project
o	Implement traversal library; add serializer/deserializer for binary trees.
o	Completion criteria: round-trip tests; iterative/recursive parity tests.
•	DSA Lab integration milestone
o	Add tree-core/ utilities used by later BST/balanced trees.
•	Meta-skills developed
o	Structural induction, recursion control.
D7 — Binary Search Trees (BST) and augmentations (Core)
•	Time: 12h (~0.8w)
•	Dependencies: D6, F2–F3
•	What to master (atomic components)
o	BST invariant; search/insert/delete; deletion cases.
o	Complexity: average vs worst case; when BST degenerates.
o	Augmentations: subtree size (order statistics), subtree sum/min/max.
o	Successor/predecessor; range queries concept.
•	Free resources
o	R1 + R9 + R6 BST content. (MIT OpenCourseWare)
•	Independent validation project
o	Implement BSTMap<K,V> + augmentation subtree_size.
o	Completion criteria: randomized insert/delete tests; order-statistics queries correct; include invariant check method.
•	DSA Lab integration milestone
o	Add bst/ module; document worst-case failure modes.
•	Meta-skills developed
o	Correctness under mutation, invariant enforcement.
D8 — Disjoint Set Union (Union-Find / DSU) (Core)
•	Time: 8h (~0.5w)
•	Dependencies: F3
•	What to master (atomic components)
o	Set representation; union by rank/size; path compression.
o	Amortized analysis intuition (inverse Ackermann, informal ok here).
o	Applications: connectivity, Kruskal, dynamic connectivity (preview).
•	Free resources
o	R1 + R9 DSU + R11 reference. (MIT OpenCourseWare)
•	Independent validation project
o	Implement DSU with union by size + path compression.
o	Completion criteria: passes randomized connectivity sequences; instrument to count parent-pointer traversals before/after compression.
•	DSA Lab integration milestone
o	Add dsu/ module used later in MST and clustering.
•	Meta-skills developed
o	Amortized reasoning, instrumentation.
D9 — Tries and prefix structures (Important)
•	Time: 8h (~0.5w)
•	Dependencies: D6, D1
•	What to master (atomic components)
o	Trie node structure; terminal markers; memory tradeoffs.
o	Prefix queries; autocomplete; lexicographic traversal.
o	Variants (Optional inside this subdomain): compressed trie/radix tree; ternary search tree.
•	Free resources
o	R4 + R11 + R13 for intuition. (opendatastructures.org)
•	Independent validation project
o	Implement trie for lowercase strings with: insert, delete, prefix count, autocomplete top-k (simple heuristic).
o	Completion criteria: correctness tests; performance comparison vs hash set for prefix queries.
•	DSA Lab integration milestone
o	Add trie/ module; include memory-usage note.
•	Meta-skills developed
o	Data modeling, memory-performance tradeoffs.
D10 — Graph representations and core graph tooling (Core)
•	Time: 10h (~0.7w)
•	Dependencies: D1, D3, F2
•	What to master (atomic components)
o	Graph models: directed/undirected, weighted/unweighted, multigraph.
o	Representations: adjacency list, adjacency matrix, edge list; conversion between them.
o	Complexity tradeoffs: dense vs sparse; memory implications.
o	Input parsing at scale; iterative traversals to avoid recursion depth issues.
•	Free resources
o	R1 graph sections + R6 graph representations + R11. (MIT OpenCourseWare)
•	Independent validation project
o	Implement Graph with multiple backends + iterators for edges/neighbors.
o	Completion criteria: supports 10^5 edges without crashing; conversion correctness tests; benchmark adjacency list vs matrix for traversal.
•	DSA Lab integration milestone
o	Add graph-core/ module used by all later graph algorithms.
•	Meta-skills developed
o	Abstraction (interfaces), algorithm engineering.
P1R — Review & integration: Data structures synthesis (Important)
•	Time: 16h (~1.1w)
•	Dependencies: D1–D10
•	Review targets
o	Implement from memory: heap, hash table, DSU (no notes), then compare.
o	Build a “DS chooser” decision chart: constraints → DS.
o	Solve 20 mixed DS problems; categorize by pattern (stack/queue/hash/tree/graph).
•	Restructure method
o	Create a single unified invariant document: “what must always be true” per DS.
•	Independent validation project
o	DSA Lab DS module v1: ship a tagged release with full tests and benchmarks.
o	Completion criteria: all DS pass randomized differential testing; written docs for each DS; benchmark report committed.
•	DSA Lab milestone
o	Tag release v1-data-structures.
________________________________________
Phase 2 (Weeks 13–24, 180h): Core Algorithms & Paradigms
A1 — Sorting: comparison + non-comparison (Core)
•	Time: 20h (~1.3w)
•	Dependencies: D1, D5, F3
•	What to master (atomic components)
o	Comparison sorts: insertion/selection, merge, quick, heap; stability; in-place vs extra memory.
o	Partition schemes; pivot strategies; worst-case quicksort.
o	Non-comparison: counting sort, radix sort (LSD/MSD) under constraints.
o	Lower bound: Ω(n log n) comparisons; when it applies.
•	Free resources
o	R1 sorting lectures + R6 quicksort/mergesort + R5 sorting chapter. (MIT OpenCourseWare)
o	R13 to validate intuition. (visualgo.net)
•	Independent validation project
o	Implement 6 sorts + a benchmark harness and adversarial inputs.
o	Completion criteria: stability tests; worst-case quicksort demonstration; report on when radix wins.
•	DSA Lab integration milestone
o	Add sorting/ module + visualizer for 2 sorts (optional but measurable).
•	Meta-skills developed
o	Lower-bound reasoning, empirical validation.
A2 — Searching, binary search mastery, selection (Core)
•	Time: 12h (~0.8w)
•	Dependencies: D1, F3
•	What to master (atomic components)
o	Binary search variants: first true/last true, lower_bound/upper_bound, search on answer.
o	Selection: quickselect; deterministic median-of-medians (Important).
o	Pitfalls: overflow in mid, infinite loops, invariants.
•	Free resources
o	R1 + R6 selection content + R11 for patterns. (MIT OpenCourseWare)
•	Independent validation project
o	Implement a “binary search cookbook” with 8 templates + tests.
o	Implement quickselect + deterministic select.
o	Completion criteria: solve 15 “search on answer” problems; every solution states the monotonic predicate explicitly.
•	DSA Lab integration milestone
o	Add searching/ templates with invariant assertions.
•	Meta-skills developed
o	Predicate thinking, invariant precision.
A3 — Recursion, backtracking, pruning (Core)
•	Time: 16h (~1.1w)
•	Dependencies: F2, D3, D6
•	What to master (atomic components)
o	Recursion trees; base cases; stack depth control.
o	Backtracking framework: choose → explore → unchoose.
o	Pruning: constraints propagation, bounding, symmetry breaking.
o	Iterative simulation with explicit stack when needed.
•	Free resources
o	R1 + R5 recursion/DP framing + R14 practice. (MIT OpenCourseWare)
•	Independent validation project
o	Implement N-Queens + Sudoku solver + subset generation; include pruning heuristics.
o	Completion criteria: runtime improvement demonstrated (with/without pruning); write-up explains pruning correctness.
•	DSA Lab integration milestone
o	Add backtracking/ module + a small search visualizer (optional).
•	Meta-skills developed
o	Search-space modeling, proof of pruning safety.
A4 — Divide & conquer paradigms (Core)
•	Time: 16h (~1.1w)
•	Dependencies: F3, A3
•	What to master (atomic components)
o	D&C skeleton: split → solve → combine; recurrence derivation.
o	Classic problems: inversions count, closest pair (Optional), Karatsuba/Strassen (Optional).
o	Master theorem boundaries; when it doesn’t apply.
•	Free resources
o	R2 divide-and-conquer lectures + R6 D&C content + R5. (MIT OpenCourseWare)
•	Independent validation project
o	Implement inversion counting and at least one “non-trivial combine” algorithm.
o	Completion criteria: recurrence derived and solved; correctness proof includes combine-step invariant.
•	DSA Lab integration milestone
o	Add divide_conquer/ module and recurrence notes.
•	Meta-skills developed
o	Recurrence modeling, compositional proofs.
A5 — Greedy algorithms + proof patterns (Core)
•	Time: 20h (~1.3w)
•	Dependencies: F2–F3, D5
•	What to master (atomic components)
o	Greedy-choice property and optimal substructure (without confusing them).
o	Proof patterns: exchange argument, cut property, matroid intuition (Optional depth).
o	Canonical problems: interval scheduling, Huffman coding, MST (Prim/Kruskal correctness).
•	Free resources
o	R2 greedy lectures + R6 greedy playlist segments + R5. (MIT OpenCourseWare)
•	Independent validation project
o	Implement: interval scheduling, Huffman coding, MST (Kruskal + Prim).
o	Completion criteria: each has a written correctness proof (exchange or cut argument) and complexity analysis.
•	DSA Lab integration milestone
o	Add greedy/ module with proof notes and counterexamples to “tempting wrong greedies”.
•	Meta-skills developed
o	Proof craft, “why greedy works” discipline.
A6 — Dynamic programming (DP): state design → optimization (Core)
•	Time: 40h (~2.7w)
•	Dependencies: A3, F2–F3
•	What to master (atomic components)
o	DP design workflow: define state, transitions, base cases, order, reconstruction.
o	1D DP: fib variants, house robber, LIS (O(n^2) then O(n log n) concept).
o	2D DP: edit distance, LCS, knapsack, grid paths.
o	Graph DP: DAG DP, tree DP basics.
o	Memoization vs tabulation; complexity by counting states/transitions.
o	Common failure: hidden exponential via huge state space.
•	Free resources
o	R2 + R6 (Algorithms Illuminated Part 3 DP) + R5 DP chapters + R12 curated practice. (MIT OpenCourseWare)
•	Independent validation project
o	Implement 12 canonical DPs with reconstruction; include at least:
	knapsack, edit distance, LIS, interval DP, tree DP, bitmask DP (small).
o	Completion criteria: each DP has a state definition + transition proof; solve 25 DP problems across difficulties.
•	DSA Lab integration milestone
o	Add dp/ module + DP-table visualizer for one 2D DP.
•	Meta-skills developed
o	Abstraction (state compression), reasoning (optimal substructure), communication (state definitions).
A7 — Graph traversal, components, DAG algorithms (Core)
•	Time: 28h (~1.9w)
•	Dependencies: D10, D3, F2–F3
•	What to master (atomic components)
o	BFS/DFS; iterative DFS to avoid recursion limits.
o	Topological sort; DAG DP entry points.
o	Connected components (undirected); bipartite check.
o	Strongly connected components (Kosaraju/Tarjan); condensation DAG.
o	Bridges + articulation points (Important).
•	Free resources
o	R1 graph algorithms + R6 SCC/toposort + R11 implementation notes + R12 ladder. (MIT OpenCourseWare)
•	Independent validation project
o	Implement BFS, DFS, topo sort, SCC, bridges/articulation.
o	Completion criteria: verify on random graphs + known corner cases; include a generator for adversarial graphs (deep chains, dense subgraphs).
•	DSA Lab integration milestone
o	Add graph_algorithms/ core traversal suite.
•	Meta-skills developed
o	Invariant reasoning on graphs, robustness to edge cases.
A8 — Shortest paths + MST + union-find applications (Core)
•	Time: 20h (~1.3w)
•	Dependencies: D5, D8, D10, A7
•	What to master (atomic components)
o	Dijkstra (nonnegative weights) with indexed PQ; correctness proof via greedy invariant.
o	Bellman–Ford (negative edges), negative cycle detection.
o	Floyd–Warshall (all-pairs) and its DP interpretation.
o	MST: Kruskal (DSU), Prim (PQ), cut property.
o	Optional extensions: Johnson’s algorithm, 0–1 BFS, SPFA pitfalls.
•	Free resources
o	R1 + R6 shortest paths + R11 reference. (MIT OpenCourseWare)
•	Independent validation project
o	Implement: Dijkstra (with decrease-key), Bellman–Ford, Floyd–Warshall, Kruskal, Prim.
o	Completion criteria: correctness proof sketches for Dijkstra + Kruskal; benchmark Dijkstra variants (binary heap vs indexed PQ).
•	DSA Lab integration milestone
o	Add shortest_paths/ + mst/ modules; add visualization for BFS vs Dijkstra on same graph.
•	Meta-skills developed
o	Algorithm-DS integration, proof discipline.
P2R — Review & integration: Core algorithms consolidation (Important)
•	Time: 8h (~0.5w)
•	Dependencies: A1–A8
•	Review targets
o	Re-solve from memory: one DP, one graph shortest-path, one greedy proof.
o	Build a “paradigm classifier”: for any new problem, map to D&C/greedy/DP/graph search.
•	Restructure method
o	Create a single page: “common invariants by paradigm” (DP recurrence invariant, greedy cut/exchange, graph visitation invariant).
•	Independent validation project
o	Algorithm library v1: integrate all implementations into stable APIs.
o	Completion criteria: 60-problem mixed set solved; ≥80% solved without looking up solutions; every miss has a documented failure reason.
•	DSA Lab milestone
o	Tag release v2-core-algorithms.
________________________________________
Phase 3 (Weeks 25–34, 150h): Advanced Data Structures + Strings + Geometry
X1 — Balanced search trees + augmentations (Important)
•	Time: 24h (~1.6w)
•	Dependencies: D7, F2–F3
•	What to master (atomic components)
o	Rotations; height invariants.
o	AVL: balance factor; rebalancing cases.
o	Red–black trees: coloring invariants; insertion/deletion fixups (hard; do not fake it).
o	Treaps (Optional): randomized balancing via heap priority.
o	Splay trees (Optional): amortized access intuition.
o	Augmentations: order statistics, interval trees, segment-tree-like augmentation ideas.
•	Free resources
o	R6 balanced trees segments + R9 AVL/rotations + R11 augmentation notes. (YouTube)
•	Independent validation project
o	Implement one fully correct balanced BST (AVL or red–black) + one augmentation (subtree size).
o	Completion criteria: 100k randomized ops with invariant checks after each; performance comparison vs unbalanced BST.
•	DSA Lab integration milestone
o	Add balanced_bst/ module; include invariant-check function callable in tests.
•	Meta-skills developed
o	Correctness under complex invariants; disciplined implementation.
X2 — Range query data structures: Fenwick, segment tree, sparse table (Important)
•	Time: 28h (~1.9w)
•	Dependencies: D1, F3, X1 (optional but helpful)
•	What to master (atomic components)
o	Fenwick tree (BIT): prefix sums; point updates; range queries via prefix differences.
o	Segment tree: build/query/update; lazy propagation for range updates.
o	Sparse table (Optional): idempotent RMQ; O(1) queries, O(n log n) preprocess.
o	Coordinate compression; offline vs online queries.
•	Free resources
o	R9 (Fenwick, sparse table videos) + R11 (segment tree patterns) + R12 practice ladder. (YouTube)
•	Independent validation project
o	Implement BIT + segment tree with lazy propagation + sparse table for RMQ.
o	Completion criteria: solve 20 range-query problems; include at least 5 with lazy propagation; performance report.
•	DSA Lab integration milestone
o	Add range_ds/ module and benchmarks for query/update regimes.
•	Meta-skills developed
o	Abstraction (query monoids), performance engineering.
X3 — Advanced DS concepts: persistence, rollback, amortized analysis (Optional)
•	Time: 24h (~1.6w)
•	Dependencies: F3, X2
•	What to master (atomic components)
o	Persistent structures (partial persistence): persistent stack/array; persistent segment tree concept.
o	DSU with rollback (Important in competitive contexts).
o	Amortized proofs (formal): accounting and potential method; apply to dynamic arrays, splay (concept), DSU heuristics.
o	Retroactive data structures (Optional): conceptual understanding.
•	Free resources
o	R8 (MIT 6.851 advanced DS topics) + R4 for foundational DS reasoning. (YouTube)
•	Independent validation project
o	Implement DSU with rollback or persistent segment tree (choose one).
o	Completion criteria: solve 5 problems that require rollback/persistence; include a potential-method style amortized note for one DS.
•	DSA Lab integration milestone
o	Add advanced_ds/ module + one deep technical note.
•	Meta-skills developed
o	Mathematical maturity (potential functions), design under constraints.
X4 — String algorithms: KMP/Z, hashing, suffix structures, Aho–Corasick (Important)
•	Time: 30h (~2.0w)
•	Dependencies: D1, D9, F2–F3
•	What to master (atomic components)
o	Prefix-function (KMP) and Z algorithm; pattern matching.
o	Rolling hash: collision modeling; double-hash strategy; adversarial considerations.
o	Trie-based multi-pattern matching: Aho–Corasick (Optional but high-value).
o	Suffix array + LCP; applications: longest repeated substring, unique substrings.
o	Optional: suffix automaton; suffix tree (conceptual).
•	Free resources
o	R9 (suffix array/LCP content) + R11 string articles + R5 strings. (YouTube)
•	Independent validation project
o	Implement: KMP, Z, rolling hash substring queries, suffix array + LCP; optionally Aho–Corasick.
o	Completion criteria: solve 15 string problems; include at least 3 where naive is O(n^2) and your solution is near-linear.
•	DSA Lab integration milestone
o	Add strings/ module + collision analysis note for hashing.
•	Meta-skills developed
o	Formalization, adversarial thinking.
X5 — Bit manipulation and bitset techniques (Optional)
•	Time: 12h (~0.8w)
•	Dependencies: D1, F3
•	What to master (atomic components)
o	Bitwise ops; masks; subset iteration; popcount; lowbit tricks.
o	Bitset DP speedups; meet-in-the-middle concept.
o	Optional: XOR basis (linear basis over GF(2)).
•	Free resources
o	R11 bit tricks + R14 practice. (CP Algorithms)
•	Independent validation project
o	Implement bitmask DP for at least one NP-ish small-n problem; implement XOR basis (optional).
o	Completion criteria: solve 10 bitmask/bitset problems; include one micro-optimization report (bitset vs boolean array).
•	DSA Lab integration milestone
o	Add bit/ utilities and a “mask iteration” template.
•	Meta-skills developed
o	Low-level performance reasoning.
X6 — Computational geometry basics (Optional)
•	Time: 16h (~1.1w)
•	Dependencies: F2–F3
•	What to master (atomic components)
o	Orientation / cross product; segment intersection; numeric robustness.
o	Convex hull (Graham scan or monotone chain).
o	Line sweep concept (Optional): event ordering and active set idea.
•	Free resources
o	R8 includes geometric structures topics; R11 geometry references. (YouTube)
•	Independent validation project
o	Implement convex hull + segment intersection; test random point sets.
o	Completion criteria: passes degenerate cases (collinear points, duplicates); solves 5 geometry problems.
•	DSA Lab integration milestone
o	Add geometry/ module with robust orientation handling notes.
•	Meta-skills developed
o	Mathematical modeling, numerical caution.
P3R — Review & integration: Advanced DS synthesis (Important)
•	Time: 16h (~1.1w)
•	Dependencies: X1–X6
•	Review targets
o	Implement from memory: segment tree with lazy propagation (minimal API).
o	Re-derive: KMP prefix function and suffix array construction logic (high-level).
o	Solve a mixed set: 10 range-query + 10 string problems.
•	Restructure method
o	Build “query algebra” notes: how monoids/idempotence drive DS choice (Fenwick vs segtree vs sparse table).
•	Independent validation project
o	DSA Lab advanced module release: range DS + strings integrated.
o	Completion criteria: stable APIs; benchmark report on at least 3 workloads; docs with invariants.
•	DSA Lab milestone
o	Tag release v3-advanced-ds.
________________________________________
Phase 4 (Weeks 35–44, 150h): Advanced Algorithms + Complexity
Y1 — Network flow and min-cut (Important)
•	Time: 40h (~2.7w)
•	Dependencies: D10, A7–A8, F2–F3
•	What to master (atomic components)
o	Flow definitions, conservation, residual graphs, augmenting paths.
o	Max-flow min-cut theorem (proof sketch level).
o	Algorithms: Ford–Fulkerson, Edmonds–Karp, Dinic; complexity and practical behavior.
o	Optional: push–relabel; scaling; min-cost max-flow (often needed).
o	Modeling skill: turning problems into flow networks (the real mastery).
•	Free resources
o	R2 (includes max-flow/min-cut lecture content) + MIT 6.046 network flow notes (extra). (YouTube)
o	R7 (CS261 covers flows deeply) + R10 implementation playlist. (YouTube)
•	Independent validation project
o	Implement Dinic + min-cost max-flow.
o	Solve 12 flow-modeling problems (matching, circulation with demands, min-cut variants).
o	Completion criteria: each modeling solution includes a diagram + reduction explanation; benchmark Dinic vs Edmonds–Karp on stress graphs.
•	DSA Lab integration milestone
o	Add flow/ module + flow visualizer (optional) + modeling cookbook.
•	Meta-skills developed
o	Reduction skill, algorithm engineering, proof maturity.
Y2 — Matching and assignment (Important)
•	Time: 20h (~1.3w)
•	Dependencies: Y1, A7
•	What to master (atomic components)
o	Bipartite matching: augmenting paths; relation to max-flow.
o	Hopcroft–Karp (Important).
o	Assignment problem + Hungarian algorithm (Optional but valuable).
•	Free resources
o	R7 (matching topics) + R10 (matching via flow) + R11 references. (YouTube)
•	Independent validation project
o	Implement Hopcroft–Karp and compare vs flow-based matching.
o	Completion criteria: solve 8 matching problems; include one assignment problem (Hungarian optional; flow formulation acceptable).
•	DSA Lab integration milestone
o	Add matching/ module; document when matching beats flow and why.
•	Meta-skills developed
o	Algorithm selection and reduction literacy.
Y3 — Linear programming basics + duality for algorithm design (Optional)
•	Time: 16h (~1.1w)
•	Dependencies: F2–F3, Y1 helpful
•	What to master (atomic components)
o	LP formulation: variables, constraints, objective; feasibility vs optimization.
o	Dual LP and weak duality; intuition for primal–dual algorithms.
o	Canonical applications: max-flow/min-cut relation; set cover relaxation (concept).
•	Free resources
o	R7 explicitly covers LP duality in algorithm design context. (YouTube)
•	Independent validation project
o	Formulate 6 problems as LPs; write the dual for 3; explain dual meaning.
o	Implement one simple primal–dual approximation (e.g., vertex cover) and validate approximation ratio empirically.
o	Completion criteria: written derivations; working code; experiment report.
•	DSA Lab integration milestone
o	Add lp_notes/ and one primal–dual implementation.
•	Meta-skills developed
o	Mathematical maturity, innovation scaffolding (design from relaxations).
Y4 — NP-completeness, reductions, complexity basics (Important)
•	Time: 24h (~1.6w)
•	Dependencies: F2, A6, Y3 optional
•	What to master (atomic components)
o	Classes: P, NP, NP-hard, NP-complete; Cook reductions.
o	Reduction mechanics: mapping instances; correctness both directions.
o	Canonical NP-complete problems: SAT/3SAT, Clique, Vertex Cover, Hamiltonian Cycle, Subset Sum/Partition.
o	What “hard” means in practice: pseudo-polynomial vs polynomial; parameter sensitivity.
•	Free resources
o	R3 (includes halting problem exposure) + R7/R6 for NP-hard topics. (MIT OpenCourseWare)
•	Independent validation project
o	Write 10 reductions (short but correct), including at least:
	3SAT → VC, 3SAT → Clique, Subset Sum ↔ Partition, VC ↔ Independent Set.
o	Implement a small SAT backtracking solver for n ≤ 50 variables as a sanity tool.
o	Completion criteria: each reduction includes mapping + proof; SAT solver solves random small instances.
•	DSA Lab integration milestone
o	Add np/ notes folder with reductions and diagrams.
•	Meta-skills developed
o	Formal reasoning, innovation axis groundwork.
Y5 — Approximation algorithms + heuristics + local search (Important)
•	Time: 20h (~1.3w)
•	Dependencies: Y4, Y3 (helpful)
•	What to master (atomic components)
o	Approximation ratio definitions; PTAS vs constant-factor.
o	Greedy approximations: vertex cover, set cover (ln n), scheduling heuristics.
o	Local search: k-exchange; when it gets stuck.
o	Empirical evaluation discipline: approximation ratio vs runtime tradeoffs.
•	Free resources
o	R7 (approximation focus in CS261) + Roughgarden NP-hard playlist. (YouTube)
•	Independent validation project
o	Implement 3 approximation/heuristic algorithms (e.g., vertex cover 2-approx, set cover greedy, TSP local search).
o	Completion criteria: for each, run ≥200 randomized instances; report observed quality distribution and worst cases found.
•	DSA Lab integration milestone
o	Add approx/ module + experiment scripts.
•	Meta-skills developed
o	Experimental design, innovation thinking (designing under hardness).
Y6 — Beyond worst-case: randomization, hashing theory, cache/online concepts (Optional)
•	Time: 10h (~0.7w)
•	Dependencies: F3, D4, A1
•	What to master (atomic components)
o	Randomized algorithms basics: expected runtime, failure probability controls.
o	Universal hashing concept; Bloom filters (revisit).
o	Cache-oblivious idea (Optional): why asymptotics miss memory hierarchy.
o	Online/adversarial viewpoint (Optional): competitive ratio awareness.
•	Free resources
o	R2 includes advanced topics like cryptography/cache-oblivious lectures; R6 includes randomized components. (MIT OpenCourseWare)
•	Independent validation project
o	Implement Bloom filter and evaluate false-positive rate vs theory.
o	One cache-sensitivity experiment: same Θ(n) algorithm variants with different locality.
o	Completion criteria: report includes predicted vs observed curves.
•	DSA Lab integration milestone
o	Add beyond_worst_case/ notes + experiments.
•	Meta-skills developed
o	Probabilistic reasoning, empirical skepticism.
P4R — Review & integration: Advanced algorithms synthesis (Important)
•	Time: 20h (~1.3w)
•	Dependencies: Y1–Y6
•	Review targets
o	Re-derive max-flow min-cut theorem proof skeleton.
o	Solve 10 reductions/approx modeling exercises (not coding).
o	Implement from memory: Dinic core loop + residual update.
•	Restructure method
o	Build “reduction atlas”: problem → known hard core → reduction pattern → approximation approach.
•	Independent validation project
o	DSA Lab advanced algorithms release: flow + NP + approx integrated.
o	Completion criteria: one “modeling cookbook” doc; benchmarks; at least 5 fully worked flow reductions.
•	DSA Lab milestone
o	Tag release v4-advanced-algorithms.
________________________________________
Phase 5 (Weeks 45–52, 120h): Innovation & Capstone Mastery
C1 — Research reading and replication protocol (Important)
•	Time: 24h (~1.6w)
•	Dependencies: all prior phases
•	What to master (atomic components)
o	Paper reading pipeline: problem setting → model assumptions → key lemma → algorithm skeleton → proof structure → complexity.
o	Replication: implement from paper, reproduce claimed results or explain gaps.
o	Write reproducible experiments: fixed seeds, controlled input families, versioned outputs.
•	Free resources
o	Use R8/R7 advanced material as paper-adjacent sources; use R11 to bridge implementation gaps. (YouTube)
•	Independent validation project
o	Pick 1 advanced algorithm topic from your existing sources (e.g., persistent DS or flow variant) and replicate it end-to-end.
o	Completion criteria: “replication report” with algorithm description, proof sketch, implementation notes, and experimental results.
•	DSA Lab integration milestone
o	Add research/replication-1/ folder with code + report.
•	Meta-skills developed
o	Scientific thinking, precision, defensible claims.
C2 — High-volume problem-solving sprint with coverage guarantees (Core)
•	Time: 40h (~2.7w)
•	Dependencies: P4R
•	What to master (atomic components)
o	Coverage across categories: DS, greedy, DP, graph, strings, range DS, flow, NP/approx.
o	Speed + accuracy without sacrificing proof: solve fast, then prove and test.
o	Post-mortem discipline: classify every miss into a fixable failure mode.
•	Free resources
o	R12 topic ladders + R14 platforms (Codeforces/AtCoder/Kattis). (USACO Guide)
•	Independent validation project
o	Solve 120 problems in 8 weeks with strict distribution:
	25 DP, 25 graph, 15 strings, 15 range DS, 15 greedy, 10 flow/matching, 15 mixed.
o	Completion criteria: ≥85% solved without editorial; every solved problem has a 5–10 line invariant/idea summary; every unsolved has post-mortem + retry.
•	DSA Lab integration milestone
o	Add “problem index” by topic with links to your own solutions and patterns.
C3 — Original contribution: design or improve an algorithm/DS (Core)
•	Time: 40h (~2.7w)
•	Dependencies: C1, C2
•	What to master (atomic components)
o	Problem selection: constrained niche where baseline is known and measurable.
o	Novelty: new heuristic, pruning rule, augmentation, or hybrid approach.
o	Evidence: proof of correctness if exact; bound/guarantee if approximate; empirical evidence either way.
•	Free resources
o	R7 approximation/LP framing supports “design space” thinking; R2/R8 for advanced ideas. (YouTube)
•	Independent validation project
o	Deliver one of:
	Exact: new DS/algorithm variant with correctness proof + complexity analysis.
	Approx/heuristic: algorithm with stated objective and failure modes + measured improvement on a benchmark suite.
o	Completion criteria: reproducible benchmark shows ≥15% improvement in at least one meaningful metric (runtime, memory, solution quality) under clearly stated conditions; write-up includes negative results too.
•	DSA Lab integration milestone
o	Add original/ module + full report + experiment harness.
C4 — Final integration: mastery defense + release (Important)
•	Time: 16h (~1.1w)
•	Dependencies: everything
•	What to master (atomic components)
o	Produce a coherent “system”: DS ↔ algorithms ↔ proofs ↔ empirical validation.
o	Present your work as a consumable artifact (docs, examples, reproducible experiments).
•	Free resources
o	R1/R2/R3 remain references for cross-checking fundamentals. (MIT OpenCourseWare)
•	Independent validation project
o	Mastery defense bundle
	25-page equivalent technical write-up (can be multiple docs).
	60-minute self-recorded lecture-style walkthrough (optional artifact).
	Final library release with tagged version and changelog.
o	Completion criteria: run-from-scratch reproducibility; third-party can execute tests+benches with one command; documentation includes invariants and proofs for core modules.
•	DSA Lab milestone
o	Tag release v5-final.
________________________________________
Meta-skill development tracking (parallel, non-optional)
•	Abstraction: D10 (graph interfaces), X2 (monoid thinking), C3 (designing new API + invariants).
•	Mathematical maturity: F2/F3 baseline, A5 greedy proofs, X3 amortized, Y3 duality, Y4 reductions.
•	Reasoning (proof + invariants): every algorithm note requires invariant + proof sketch; hardest checkpoints: X1, Y1, Y4.
•	Experimental design: F1 benchmark hygiene → D4 hashing performance → Y5 approximation evaluation → C1 replication protocol.
•	Communication: weekly 1-page note; phase reviews require “concept map” restructuring artifacts.
________________________________________
Mastery criteria (explicit thresholds)
(A) Complete comprehension + applied competence
You meet (A) only if all are true:
1.	Implementation coverage: ≥25 data structures and ≥40 algorithms implemented from scratch with tests (property tests where applicable).
2.	Proof coverage: ≥30 correctness proofs written (not handwavy) spanning greedy, DP, shortest paths, flow, and one NP-completeness reduction set.
3.	Problem-solving coverage: ≥300 problems solved total, including:
o	≥60 DP, ≥60 graph, ≥30 strings, ≥30 range DS, ≥20 flow/matching, ≥20 “hard” mixed.
4.	Performance literacy: ≥10 benchmark reports showing predicted vs observed behavior, including at least 3 cases where constant factors/cache dominate.
5.	Reliability: your library passes randomized stress tests for 10^5–10^6 operations on core DS without invariant violations.
(B) Innovation / original work capability
You meet (B) only if all are true:
1.	Replication: one end-to-end replication of an advanced algorithm/DS with reproducible experiments and a written report (C1).
2.	Original contribution: one new algorithm/DS variant or heuristic with:
o	clear problem definition and assumptions,
o	either correctness proof (exact) or approximation/behavior claim (heuristic),
o	reproducible benchmark showing ≥15% improvement in a meaningful metric under stated conditions,
o	documented failure cases.
3.	Exposition quality: at least 5 long-form technical notes (≥1500 words each) that a third party can follow to implement and validate the method without external materials.
________________________________________
Part B: ASCII/Markdown hierarchical dependency tree
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
________________________________________
Part C: JSON outline of the same tree
{
  "id": "DSA",
  "title": "Data Structures & Algorithms Mastery",
  "children": [
    {
      "id": "P0",
      "title": "Foundations",
      "children": [
        { "id": "F1", "title": "Tooling, testing, benchmarking", "priority": "Core", "hours": 12, "weeks": 0.8, "depends_on": [] },
        { "id": "F2", "title": "Discrete math + proofs", "priority": "Core", "hours": 22, "weeks": 1.5, "depends_on": ["F1"] },
        { "id": "F3", "title": "Asymptotic analysis + recurrences", "priority": "Core", "hours": 14, "weeks": 0.9, "depends_on": ["F2"] },
        { "id": "F4", "title": "Problem framing + write-ups", "priority": "Important", "hours": 6, "weeks": 0.4, "depends_on": ["F1", "F2", "F3"] },
        { "id": "P0R", "title": "Foundations review + integration", "priority": "Important", "hours": 6, "weeks": 0.4, "depends_on": ["F1", "F2", "F3", "F4"] }
      ]
    },
    {
      "id": "P1",
      "title": "Core Data Structures",
      "children": [
        { "id": "D1", "title": "Arrays + dynamic arrays + prefix sums", "priority": "Core", "hours": 10, "weeks": 0.7, "depends_on": ["F1", "F2", "F3"] },
        { "id": "D2", "title": "Linked lists", "priority": "Core", "hours": 8, "weeks": 0.5, "depends_on": ["D1", "F1"] },
        { "id": "D3", "title": "Stacks/queues/deques + monotonic patterns", "priority": "Core", "hours": 10, "weeks": 0.7, "depends_on": ["D1", "D2"] },
        { "id": "D4", "title": "Hashing + hash tables", "priority": "Core", "hours": 16, "weeks": 1.1, "depends_on": ["D1", "F3"] },
        { "id": "D5", "title": "Heaps + indexed priority queues", "priority": "Core", "hours": 12, "weeks": 0.8, "depends_on": ["D1", "F3"] },
        { "id": "D6", "title": "Trees + traversals", "priority": "Core", "hours": 10, "weeks": 0.7, "depends_on": ["D2", "F2"] },
        { "id": "D7", "title": "Binary search trees + augmentations", "priority": "Core", "hours": 12, "weeks": 0.8, "depends_on": ["D6", "F2", "F3"] },
        { "id": "D8", "title": "Union-Find (DSU)", "priority": "Core", "hours": 8, "weeks": 0.5, "depends_on": ["F3"] },
        { "id": "D9", "title": "Tries + prefix structures", "priority": "Important", "hours": 8, "weeks": 0.5, "depends_on": ["D6", "D1"] },
        { "id": "D10", "title": "Graph representations + tooling", "priority": "Core", "hours": 10, "weeks": 0.7, "depends_on": ["D1", "D3", "F2"] },
        { "id": "P1R", "title": "Data structures review + integration", "priority": "Important", "hours": 16, "weeks": 1.1, "depends_on": ["D1", "D2", "D3", "D4", "D5", "D6", "D7", "D8", "D9", "D10"] }
      ]
    },
    {
      "id": "P2",
      "title": "Core Algorithms & Paradigms",
      "children": [
        { "id": "A1", "title": "Sorting (comparison + non-comparison)", "priority": "Core", "hours": 20, "weeks": 1.3, "depends_on": ["D1", "D5", "F3"] },
        { "id": "A2", "title": "Searching + binary search variants + selection", "priority": "Core", "hours": 12, "weeks": 0.8, "depends_on": ["D1", "F3"] },
        { "id": "A3", "title": "Recursion + backtracking + pruning", "priority": "Core", "hours": 16, "weeks": 1.1, "depends_on": ["F2", "D3", "D6"] },
        { "id": "A4", "title": "Divide & conquer", "priority": "Core", "hours": 16, "weeks": 1.1, "depends_on": ["F3", "A3"] },
        { "id": "A5", "title": "Greedy algorithms + proof patterns", "priority": "Core", "hours": 20, "weeks": 1.3, "depends_on": ["F2", "F3", "D5"] },
        { "id": "A6", "title": "Dynamic programming (design + reconstruction)", "priority": "Core", "hours": 40, "weeks": 2.7, "depends_on": ["A3", "F2", "F3"] },
        { "id": "A7", "title": "Graph traversal + components + SCC + DAG", "priority": "Core", "hours": 28, "weeks": 1.9, "depends_on": ["D10", "D3", "F2", "F3"] },
        { "id": "A8", "title": "Shortest paths + MST", "priority": "Core", "hours": 20, "weeks": 1.3, "depends_on": ["D5", "D8", "D10", "A7"] },
        { "id": "P2R", "title": "Core algorithms review + integration", "priority": "Important", "hours": 8, "weeks": 0.5, "depends_on": ["A1", "A2", "A3", "A4", "A5", "A6", "A7", "A8"] }
      ]
    },
    {
      "id": "P3",
      "title": "Advanced Data Structures & Specialized Topics",
      "children": [
        { "id": "X1", "title": "Balanced BSTs + augmentations (AVL/RB/Treap/Splay)", "priority": "Important", "hours": 24, "weeks": 1.6, "depends_on": ["D7", "F2", "F3"] },
        { "id": "X2", "title": "Range DS (Fenwick/Segment/Lazy/Sparse)", "priority": "Important", "hours": 28, "weeks": 1.9, "depends_on": ["D1", "F3"] },
        { "id": "X3", "title": "Persistence + rollback + amortized proofs", "priority": "Optional", "hours": 24, "weeks": 1.6, "depends_on": ["F3", "X2"] },
        { "id": "X4", "title": "String algorithms (KMP/Z/Hash/Suffix/Aho)", "priority": "Important", "hours": 30, "weeks": 2.0, "depends_on": ["D1", "D9", "F2", "F3"] },
        { "id": "X5", "title": "Bit manipulation + bitset techniques", "priority": "Optional", "hours": 12, "weeks": 0.8, "depends_on": ["D1", "F3"] },
        { "id": "X6", "title": "Computational geometry basics", "priority": "Optional", "hours": 16, "weeks": 1.1, "depends_on": ["F2", "F3"] },
        { "id": "P3R", "title": "Advanced DS review + integration", "priority": "Important", "hours": 16, "weeks": 1.1, "depends_on": ["X1", "X2", "X3", "X4", "X5", "X6"] }
      ]
    },
    {
      "id": "P4",
      "title": "Advanced Algorithms & Complexity",
      "children": [
        { "id": "Y1", "title": "Network flow + min-cut + min-cost", "priority": "Important", "hours": 40, "weeks": 2.7, "depends_on": ["D10", "A7", "A8", "F2", "F3"] },
        { "id": "Y2", "title": "Matching + assignment", "priority": "Important", "hours": 20, "weeks": 1.3, "depends_on": ["Y1", "A7"] },
        { "id": "Y3", "title": "Linear programming + duality", "priority": "Optional", "hours": 16, "weeks": 1.1, "depends_on": ["F2", "F3"] },
        { "id": "Y4", "title": "NP-completeness + reductions", "priority": "Important", "hours": 24, "weeks": 1.6, "depends_on": ["F2", "A6"] },
        { "id": "Y5", "title": "Approximation + heuristics + local search", "priority": "Important", "hours": 20, "weeks": 1.3, "depends_on": ["Y4"] },
        { "id": "Y6", "title": "Beyond worst-case (randomization/cache/online)", "priority": "Optional", "hours": 10, "weeks": 0.7, "depends_on": ["F3", "D4", "A1"] },
        { "id": "P4R", "title": "Advanced algorithms review + integration", "priority": "Important", "hours": 20, "weeks": 1.3, "depends_on": ["Y1", "Y2", "Y3", "Y4", "Y5", "Y6"] }
      ]
    },
    {
      "id": "P5",
      "title": "Innovation & Capstone",
      "children": [
        { "id": "C1", "title": "Research reading + replication protocol", "priority": "Important", "hours": 24, "weeks": 1.6, "depends_on": ["P4R"] },
        { "id": "C2", "title": "Coverage-guaranteed problem-solving sprint", "priority": "Core", "hours": 40, "weeks": 2.7, "depends_on": ["C1"] },
        { "id": "C3", "title": "Original contribution (design/improve)", "priority": "Core", "hours": 40, "weeks": 2.7, "depends_on": ["C1", "C2"] },
        { "id": "C4", "title": "Final integration + mastery defense + release", "priority": "Important", "hours": 16, "weeks": 1.1, "depends_on": ["C3"] }
      ]
    }
  ]
}

