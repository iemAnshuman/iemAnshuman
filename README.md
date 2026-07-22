<h1 align="center">Anshuman Agrawal</h1>

<p align="center">
  <strong>HPC & AI Systems Engineer</strong><br>
  <em>Building the communication and performance layer beneath modern AI.</em>
</p>

<p align="center">
  <a href="https://github.com/TheHPXProject/hpx">
    <img src="https://img.shields.io/badge/GSoC-2026-f9ab00?style=flat-square&logo=google" alt="Google Summer of Code 2026">
  </a>
  <a href="https://github.com/TheHPXProject/hpx/pulls?q=is%3Apr+author%3AiemAnshuman+is%3Amerged">
    <img src="https://img.shields.io/badge/HPX-17%20merged%20PRs-2ea44f?style=flat-square&logo=github" alt="17 merged HPX pull requests">
  </a>
  <img src="https://img.shields.io/badge/upstream%20additions-11%2C307-0969da?style=flat-square" alt="11,307 upstream additions">
  <img src="https://img.shields.io/badge/upstream%20deletions-2%2C307-8c959f?style=flat-square" alt="2,307 upstream deletions">
</p>

---

### About

I work at the boundary of **runtime systems, distributed communication, and AI infrastructure**.

My interests include collective communication algorithms, distributed execution,
GPU communication, trace-driven performance analysis, and systems that make
machine-learning workloads faster and easier to operate.

I am currently a **Google Summer of Code 2026 contributor with the STE||AR
Group**, working on [`hpx::collectives`](https://github.com/TheHPXProject/hpx/tree/master/libs/full/collectives).

---

### Upstream work: HPX collectives

As of **July 2026**:

- **17 merged upstream pull requests**
- **11,307 additions and 2,307 deletions** across merged HPX PRs
- Implemented or extended six hierarchical collective operations
- Added distributed correctness tests, failure-path validation, and benchmarks
- Tested changes locally and on the **LSU Rostam HPC cluster**

> These numbers represent the complete GitHub diff of my merged HPX pull
> requests, including implementation, tests, documentation, and review-driven
> revisions.

#### Selected merged pull requests

| Area | Pull request | Contribution |
|---|---|---|
| Hierarchical reductions | [#7160](https://github.com/TheHPXProject/hpx/pull/7160) | Added hierarchical `all_reduce` and `all_gather` through reduce/gather and broadcast composition |
| Adaptive execution | [#7193](https://github.com/TheHPXProject/hpx/pull/7193) | Added configurable flat-collective fallback for smaller communicator sizes |
| Hierarchical exchange | [#7307](https://github.com/TheHPXProject/hpx/pull/7307) | Implemented three-phase hierarchical `all_to_all` |
| Runtime semantics | [#7326](https://github.com/TheHPXProject/hpx/pull/7326) | Unified generation handling so one communicator can safely serve mixed collectives |
| Prefix collectives | [#7343](https://github.com/TheHPXProject/hpx/pull/7343) | Added hierarchical `inclusive_scan` and `exclusive_scan` |
| Reliability | [#7359](https://github.com/TheHPXProject/hpx/pull/7359) | Hardened communicator, barrier, site, root, and generation validation |
| Payload layout | [#7375](https://github.com/TheHPXProject/hpx/pull/7375) | Flattened hierarchical gather and scatter payloads into contiguous storage |
| All-to-all layout | [#7377](https://github.com/TheHPXProject/hpx/pull/7377) | Added flat uniform and ragged carriers for hierarchical all-to-all exchange |

The initial hierarchical collective benchmark recorded a **1.34× speedup over
the flat implementation at 32 processes** for the tested single-value DGX H100
configuration.

[View all of my HPX pull requests →](https://github.com/TheHPXProject/hpx/pulls?q=is%3Apr+author%3AiemAnshuman)

---

### Current project

#### [CommCanary](https://github.com/iemAnshuman/CommCanary)

A trace-driven regression canary for distributed LLM communication.

CommCanary distils a full workload communication trace into a compact,
model-free artifact while checking that the reduction preserves:

- regression decisions;
- pairwise configuration rankings;
- latency distributions and tail behaviour;
- operation ordering, arrival skew, and compute overlap.

```text
workload trace → compile → canary → replay → compare → pass / warn / fail
