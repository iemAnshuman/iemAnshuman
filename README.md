I work on distributed runtimes and accelerator communication: collective
algorithms, GPU runtime behavior, and the measurement code around them.

Mostly C++, CUDA, HPX/MPI, Linux systems work, and performance experiments
that try to make the failure mode measurable.

### Things that exist

[**HPX**](https://github.com/TheHPXProject/hpx/pulls?q=is%3Apr+author%3AiemAnshuman+is%3Amerged) · `C++ / HPX / MPI`

56 merged upstream PRs. In `hpx::collectives`: hierarchical `all_reduce`,
`all_gather`, `all_to_all`, `inclusive_scan`, and `exclusive_scan`; unified
generation handling, flattened hierarchical payloads, hardened failure paths,
and size-based pairwise `all_to_all`.

The pairwise campaign covered 960 executions across 16–128 localities and
4 B–64 KiB per destination.

In the runtime: orderly MPI parcelport teardown, shutdown races in the TCP
sender and background threads, Dijkstra termination-probe fixes, failure
detection and killed-locality handling, the nvcc CUDA builds, and the LSU
Rostam CI.

[**HAMi host-PID broker**](https://github.com/Project-HAMi/HAMi/pull/2417) · `Go / C / CUDA`

The device plugin serves a Unix socket and reads each caller's host PID from
`SO_PEERCRED`, so HAMi-core finds it without the before/after CUDA
primary-context probe and without mounting host procfs. Server and device
plugin in [HAMi#2417](https://github.com/Project-HAMi/HAMi/pull/2417), init-time
client in [HAMi-core#354](https://github.com/Project-HAMi/HAMi-core/pull/354).
Off by default; falls back to a node-wide lock and the old probe when the
broker can't answer.

[**HAMi-core**](https://github.com/Project-HAMi/HAMi-core/pulls?q=is%3Apr+author%3AiemAnshuman+is%3Amerged) · `C / CUDA / Linux`

Replaced a post-initialization lock that stayed stuck after its owner was
killed with process-recoverable POSIX record locking, plus concurrency
regression coverage. Smaller fixes for repeated `RTLD_NEXT` lookups returning
null, rate limiting on `cuLaunchCooperativeKernel`, and the fan index and
timestamps the v2 hooks were dropping.

[**CommCanary**](https://github.com/iemAnshuman/CommCanary) · `Python`

Source-verifiable distributed-communication canaries. Turns workload traces
into replayable artifacts, then checks source correspondence, timing, rankings,
and decision behavior instead of assuming a smaller trace preserved them.

**Other upstream fixes**

- [triton#12001](https://github.com/triton-lang/triton/pull/12001) · file cache
  groups keep working after the cache dir is moved
- [dynamo#15395](https://github.com/ai-dynamo/dynamo/pull/15395) · replayed
  tokens no longer counted as prompt tokens after a request migrates


### Currently thinking about

GPU-aware communication, memory registration, runtime initialization,
symmetric-memory collectives, transport progress, and how to make performance
claims survive reproduction.

---

[writing](https://byanshuman.page) ·
[email](mailto:asquare567@gmail.com) ·
[x](https://x.com/justhuman567) ·
[linkedin](https://www.linkedin.com/in/anshuman-agrawal-65a306243)
