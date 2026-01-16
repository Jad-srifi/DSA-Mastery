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
