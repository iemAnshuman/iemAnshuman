<h1 align="center">Anshuman Agrawal</h1>

<p align="center">
  <strong>Distributed AI Systems Researcher</strong><br>
  <em>Accelerator communication, memory movement, and collective operations.</em>
</p>

<p align="center">
  <a href="https://github.com/TheHPXProject/hpx">
    <img src="https://img.shields.io/badge/GSoC-2026-f9ab00?style=flat-square&logo=google" alt="Google Summer of Code 2026">
  </a>
  <a href="https://github.com/TheHPXProject/hpx/pulls?q=is%3Apr+author%3AiemAnshuman+is%3Amerged">
    <img src="https://img.shields.io/badge/HPX-20%2B%20merged%20PRs-2ea44f?style=flat-square&logo=github" alt="20+ merged HPX pull requests">
  </a>
  <a href="https://asquare.blog">
    <img src="https://img.shields.io/badge/blog-asquare.blog-0969da?style=flat-square" alt="A Square Blog">
  </a>
</p>

---

### About

I work on **distributed AI data-plane systems**: the software that moves tensors and model state across accelerator memory, GPUs, nodes, and high-speed networks.

My interests include collective communication, GPU-aware transfers, topology-aware transport, communication–computation overlap, and reproducible performance analysis.

I am a **Google Summer of Code 2026 contributor with the STE||AR Group**, working on [`hpx::collectives`](https://github.com/TheHPXProject/hpx/tree/master/libs/full/collectives).

---

### Selected work

#### [HPX Collectives](https://github.com/TheHPXProject/hpx/pulls?q=is%3Apr+author%3AiemAnshuman)

* Implemented hierarchical `all_reduce`, `all_gather`, `all_to_all`, and prefix scans.
* Diagnosed serialization, centralized data-path, and transport-threshold bottlenecks.
* Reduced large-message `all_to_all` performance from **7.1× behind OpenMPI to approximately 1.2×**.
* Added contiguous multidimensional payloads, communicator-generation management, benchmarks, and distributed regression tests.

#### [CommCanary](https://github.com/iemAnshuman/CommCanary)

A model-free regression canary for distributed-LLM communication that preserves configuration rankings, regression decisions, and latency-tail behaviour.

```text
communication trace → canary → replay → verify
```

---

### Current focus

* Accelerator data movement and GPU-aware communication
* Collective algorithms and distributed runtime systems
* Memory registration, staging, and asynchronous transfers
* Communication–computation overlap
* Cluster-scale performance profiling

---

### Stack

`C++20` · `Python` · `CUDA` · `HPX` · `MPI` · `NCCL` · `LCI` · `Triton` · `Linux` · `Slurm`

---

<p align="center">
  <a href="mailto:asquare567@gmail.com">Email</a>
  ·
  <a href="https://asquare.blog">Blog</a>
  ·
  <a href="https://x.com/justhuman567">X</a>
  ·
  <a href="https://www.linkedin.com/in/anshuman-agrawal-65a306243">LinkedIn</a>
</p>
