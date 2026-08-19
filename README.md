I work on distributed runtimes and accelerator communication: collective
algorithms, GPU runtime behavior, and the measurement code around them.

Mostly C++, CUDA, HPX/MPI, Linux systems work, and performance experiments
that try to make the failure mode measurable.

### Things that exist

[**hpx::collectives**](https://github.com/TheHPXProject/hpx/pulls?q=is%3Apr+author%3AiemAnshuman+is%3Amerged) · `C++ / HPX / MPI`

27 merged upstream PRs. Added hierarchical `all_reduce`, `all_gather`,
`all_to_all`, `inclusive_scan`, and `exclusive_scan`; unified generation
handling, flattened hierarchical payloads, hardened failure paths, and added
size-based pairwise `all_to_all`.

The pairwise campaign covered 960 executions across 16–128 localities and
4 B–64 KiB per destination.

[**CommCanary**](https://github.com/iemAnshuman/CommCanary) · `Python`

Source-verifiable distributed-communication canaries. Turns workload traces
into replayable artifacts, then checks source correspondence, timing, rankings,
and decision behavior instead of assuming a smaller trace preserved them.

[**HAMi-core**](https://github.com/Project-HAMi/HAMi-core/pulls?q=is%3Apr+author%3AiemAnshuman) · `C / CUDA / Linux`

Fixed a post-initialization lock that could remain stuck after its owner was
killed, replacing that path with process-recoverable POSIX record locking and
adding concurrency regression coverage.

### Current work

[**HAMi host-PID broker**](https://github.com/Project-HAMi/HAMi-core/pull/251) · `C / CUDA`
Host-PID discovery without the temporary CUDA primary-context probe, plus
CUDA-context accounting and fallback hardening.

[**vLLM symmetric memory**](https://github.com/vllm-project/vllm/pull/50182) · `Python / CUDA`
Fixing `all_reduce` dispatch so two-shot symmetric-memory communication does
not incorrectly depend on multicast support.

[**WasmEdge fault handling**](https://github.com/WasmEdge/WasmEdge/pull/5214) · `C++ / POSIX`
Working on signal-handler, alternate-stack, and `sigreturn` correctness for
embedded runtimes.

### Earlier

[**high-performance-deep-learning**](https://github.com/iemAnshuman/high-performance-deep-learning) · `Python / Triton / C++`

Fused Triton kernels, MPI ring all-reduce, gradient bucketing, INT4 packing,
and roofline-style performance experiments.

### Currently thinking about

GPU-aware communication, memory registration, runtime initialization,
symmetric-memory collectives, transport progress, and how to make performance
claims survive reproduction.

---

[blog](https://asquare.blog) ·
[email](mailto:asquare567@gmail.com) ·
[x](https://x.com/justhuman567) ·
[linkedin](https://www.linkedin.com/in/anshuman-agrawal-65a306243)
