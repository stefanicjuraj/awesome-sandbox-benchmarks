---
name: sandbox-benchmarks
description: >-
  Answers questions about sandbox provider benchmarks using only README.md in
  this repository: creation TTI (sequential, burst, staggered), npm weekly
  downloads, agent evaluation, devtool arena, pricing (CPU, memory, storage),
  isolation, and package security. Use when the user has or shares this
  benchmark README and wants comparisons, metrics, or methodology without raw
  JSON or maintainer tooling.
---

# Sandbox benchmarks

## When to use

Apply when someone asks about **sandbox providers**, **benchmarks**, or **metrics** and the **only** authoritative material available is this repository’s **`README.md`**.

## Authoritative source

1. If this repository (or a fork with the same `README.md`) is available: read **`README.md`** at the **repository root**.
2. Otherwise: if there is no `README.md` available, ask them to open or paste it.

## README

Use `README.md` headings as the index:

| Section                        | What it contains                                                               |
| :----------------------------- | :----------------------------------------------------------------------------- |
| **Sandbox Providers**          | Directory: website, docs, GitHub per provider                                  |
| **Sandbox Creation Benchmark** | **Sequential**, **Burst**, **Staggered**: median / P95 / P99 TTI, success rate |
| **NPM Registry Downloads**     | Package links, weekly downloads                                                |
| **Agent Evaluation**           | Time, tool calls, friction, errors, cost, docs score, grade                    |
| **Agent Friction Evaluation**  | Link to external evaluation repo only (no score table in README)               |
| **Devtool Arena**              | Score, grade, eval/discovery/cost/calls/errors/time, feature columns           |
| **Pricing**                    | Overview table plus **CPU**, **Memory**, **Storage**                           |
| **Isolation**                  | Virtualization / isolation technology per provider                             |
| **Security**                   | Package quality, malware, licenses, vulnerabilities                            |

Do not add measurement details, hardware, regions, or statistical methods that the README does not state.

## Answering rules

1. Use **only** tables and prose in the README. Do not infer trends, “usually,” or industry claims beyond what is printed.
2. Name **providers** and quote **cell values** exactly as in the README (units, success rates, grades, etc.).
3. For **provenance**, cite the **source lines** under each table. Do not claim newer data than those links represent.
4. When **comparing** providers, order by the **columns** the question implies and say which column you used.

## Response shape

1. **Direct answer** with the relevant numbers or facts from the README.
2. **Pointer:** README section path (e.g. Sandbox Creation Benchmark → Burst Benchmark).
3. **Optional:** the **external URL** from the README footnote for that table if they need the primary reference.
