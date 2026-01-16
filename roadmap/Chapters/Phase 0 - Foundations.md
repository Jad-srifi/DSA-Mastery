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
