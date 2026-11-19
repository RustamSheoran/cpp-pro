# Three Low-Budget C++ Systems Projects Built for HFT Engineering Hiring

To make a senior engineer at Citadel Securities, Optiver, Hudson River Trading (HRT), Jump Trading, Tower Research Capital, or IMC Trading look past a Tier-3 college pedigree, your portfolio must demonstrate how modern C++ maps onto Linux internals, CPU caches, atomic memory models, and network interfaces under realistic market stress.

Rather than building three variations of a toy matching engine, build **three distinct, composable production-grade systems** at **₹0 mandatory hardware cost** using free open-source tooling and authentic historical exchange binary archives:

1. **itch-xsk**: A deterministic NASDAQ TotalView-ITCH 5.0 and MoldUDP64 market data feed handler, gap-recovery engine, and cache-optimal Level-3 (L3) order book benchmarking Linux `recvmmsg`, `io_uring`, and `AF_XDP`.
2. **shmbus-mc**: A lock-free shared-memory IPC library and event-sourced sequencer whose atomic primitives are boundedly model-checked under weak memory models with GenMC and audited for cache-line contention via Linux `perf c2c` and Intel Processor Trace / hardware execution tracing.
3. **ouch-risk-sim**: A compile-time (`constexpr`) NASDAQ OUCH 5.0 execution gateway, AVX2 SIMD pre-trade risk firewall, custom slab allocator, and queue-aware historical replay engine.

Together, these three repositories span the inbound, inter-process, and outbound software stack of an electronic market-making firm without duplicating scope.

---

### Methodological Calibration & Engineering Credibility

On consumer hardware, absolute nanosecond figures cannot be equated to colocated servers equipped with FPGA or kernel-bypass NICs. Your credibility rests on:

- **Relative Architectural Deltas**: Measurable performance gains against naive baseline implementations.
- **Hardware-Counter Evidence**: Empirical data tracking L1/LLC cache misses, dTLB misses, branch mispredictions, and cache-line bouncing (`HITM`).
- **Formal Weak-Memory Verification**: Mathematically proving atomic synchronization primitives free of data races under weak memory models.
- **Open-Loop Tail Latency**: Robust latency distributions ($p50$, $p90$, $p99$, $p99.9$) isolated to worst-burst microburst windows, eliminating coordinated omission.
- **Interview Gate Reality**: Standout systems engineering repositories can earn engineer-backed referrals and dominate technical onsite rounds, but they do not replace the timed algorithmic online assessments (OAs) that top Indian and global HFT firms enforce as an initial gate.

---

## What Top HFT Firms Actually Hire For: Verified Evidence vs. Industry Folklore

Public technical disclosures vary significantly across trading firms, so rigorous preparation requires separating official engineering statements from secondary aggregator listings and community anecdotes:

- **Primary Engineering Publications**: Citadel Securities and Jane Street publish extensive primary engineering blogs and conference talks.
- **Aggregated Job Context**: Complete official job descriptions for Optiver New York and IMC Trading Mumbai were inaccessible in public web indexes during this research, requiring reliance on Optiver's official technology blog, CppCon keynote summaries, and partial indexed job excerpts.
- **The Jane Street Production Stack**: Jane Street warrants a specific warning for C++ applicants: its core trading stack is written in **OCaml** rather than C++, though its engineering talks emphasize identical low-level systems fundamentals: unboxed memory layouts, CPU microarchitecture (hosting Compiler Explorer creator Matt Godbolt), formal verification of network packet parsers, and nanosecond-scale hardware execution tracing via its open-source `magic-trace` tool.

### Documented Technical Expectations by Firm

| Firm | Publicly Documented Technical Expectations | Primary Stack & Protocol Signals | Evidence Source Quality & Caveats |
| :--- | :--- | :--- | :--- |
| **Citadel Securities** | Low-latency C++ (including early C++26 adoption and heavy constexpr usage); cache-line trampling, TLB misses, branch-heavy loops, allocator fragmentation; kernel bypass, NUMA-aware allocation, DPDK vs. std::execution; market data feed handlers, order book construction, determinism, idempotency, state replay, and reconciliation. | Modern C++ (C++20/23/26), Linux, exchange protocols (**ITCH, PITCH, iMpact, OUCH**), FPGA co-design. | High - official career perspectives, official Market Data Engineer JD, and an eFinancialCareers summary of remarks by Carl Cook, Herb Sutter, and Timur Doumler. |
| **Optiver** | Designing low-latency trading systems at the architectural level; concurrent data structures; optimizing algorithms and data structures; going beyond language syntax to work effectively with the OS, hardware, and network stack; balancing latency against research iteration speed. | C++ (2+ years low-latency preferred for experienced tracks), C# for trading GUIs, Linux. | Moderate - official Optiver technology blog and David Gross CppCon 2024 keynote summary; full New York C++ JD page was inaccessible. |
| **Hudson River Trading** | Advanced daily C++ usage; UNIX/Linux internals, system and processor performance, and network communication; articulating software designs from high-level abstractions down to step-by-step algorithms; distributed infrastructure and interfacing with FPGAs/ASICs. | C++, Python, and Rust in adjacent teams; Linux. | Moderate - third-party job aggregator reposting of an HRT Software Engineer (C++) listing and public Core Developer accounts. |
| **Jump Trading** | Strong C++ on Linux; data structures, threading models, OS internals, TCP/UDP multicast, kernel bypass, and bare-metal debugging; full live trading pipeline ownership (market data handling, order entry, and order lifecycle); open-source contributions and competitive programming noted as bonuses. | C++, Rust (growing), Linux, Python. | Moderate-High - campus intern and experienced Market Data / Core Developer listings on public recruiting boards. |
| **Tower Research Capital** | Modern C++, Linux systems programming, data structures and algorithms, computer networks, concurrency and multithreading, computer architecture, performance optimization, debugging and profiling; explicitly notes no prior financial markets knowledge is required for graduates. | Modern C++, Linux, Python (Gurugram Core Engineering & Graduate SWE tracks). | Moderate - Indian job/internship aggregator summaries of Gurugram graduate and intern postings and typical 5-round selection flow. |
| **IMC Trading** | Low-latency trading environment, strong academic computer science fundamentals, C++ engineering in Mumbai and Amsterdam offices. | C++, low-latency systems. | Low in public text - full official Mumbai C++ JD was inaccessible; limited to search-indexed excerpts. |
| **Jane Street** | Deep systems reasoning, unboxed memory representations and cache effects, CPU microarchitecture, formal verification of network data-plane parsers, and hardware-level latency diagnosis via Intel Processor Trace (magic-trace). | OCaml (primary), hardware/FPGA, Linux perf/Intel PT tooling. | High for engineering culture (official tech talks and engineering blog), though C++ is not its primary production trading language. |

---

### The Three Evidentiary Tiers

Distinguishing three evidentiary tiers keeps your engineering roadmap grounded rather than chasing folklore:

#### Tier 1: Explicitly Documented Hiring Requirements
Consistently emphasizes hardware-sympathetic engineering and failure resilience over encyclopedic language trivia:
- **Carl Cook (Citadel Securities Panel)**: Observed that writing fast code is relatively straightforward, whereas predicting production behavior is hard because hardware-level "hidden things" (cache-line trampling, TLB misses, branch-heavy loops, and allocator fragmentation) degrade latency.
- **Herb Sutter (Technical Fellow)**: Recounted replacing a heavily templated library modeled on Andrei Alexandrescu's Modern C++ design with concrete types because template instantiation severely slowed compile times.
- **Timur Doumler**: Highlighted heavy production reliance on `constexpr`.
- **Citadel Securities Engineering Overview**: Stresses framing constraints before coding, making state transitions explicit and replayable, and guaranteeing idempotency and reconciliation across mid-flight failures.

#### Tier 2: Repeatedly Observed Industry Expectations
Drawn with appropriate caution from interview preparation guides, aggregator listings, and candidate discussions, pointing to a multi-round technical funnel:
- **Initial Filter**: Timed coding assessments covering algorithms and data structures.
- **Deep Technical Probes**: Probing the C++ memory model (acquire/release/relaxed), false sharing, virtual dispatch (`vptr`/`vtable` indirection), lock-free SPSC ring buffers, OS internals, and socket programming.
- **Hiring Realities in India**: Campus and off-campus entry into top HFT firms heavily favors IIT graduates or high competitive-programming ratings (such as Codeforces 1900+ cited for certain quant/HFT intern tracks), making off-campus Tier-3 hiring difficult without exceptional systems proof or a stepping-stone C++ engineering role.

#### Tier 3: Principal Systems Engineer Perspective
The vast majority of student "HFT portfolio projects" fail a three-minute GitHub audit for predictable reasons:
- **Common Amateur Traps**:
  - Allocating heap nodes (`std::map`, `std::list`, `std::shared_ptr`) on the hot path.
  - Ignoring binary endianness and network packet loss.
  - Running closed-loop microbenchmarks that hide tail latency.
  - Claiming "lock-free correctness" despite subtle data races under weak memory ordering.
- **What Stands Apart Immediately**:
  - Ingesting **authentic binary exchange data**.
  - Verifying **bounded atomic correctness with a formal model checker**.
  - Auditing **assembly and hardware performance counters**.
  - Documenting **honest negative results and consumer-hardware limits**.

---

## The Three Selected Projects, Ranked by Hiring Impact

Each project below was screened against ten weighted criteria:
- Technical depth
- HFT relevance
- C++ mastery
- Originality
- Benchmarkability
- Verifiable correctness
- ₹0 mandatory cost
- Solo feasibility
- Interview/resume signal
- Potential for meaningful open-source contribution

### Technology Choices & Justification
- **AF_XDP over DPDK**: AF_XDP is prioritized over DPDK as the default kernel-bypass path because AF_XDP runs natively across Linux `veth` pairs at ₹0 while teaching authentic eBPF redirection and 4-ring UMEM buffer management, whereas DPDK's poll-mode driver advantage requires dedicated physical NICs.
- **NASDAQ OUCH 5.0 over FIX**: OUCH 5.0 is chosen over legacy ASCII FIX because binary execution gateways directly mirror modern low-latency exchange connectivity cited in Citadel Securities job specifications.

### Summary Comparison Matrix

| Rank | Project Name | Core HFT Domain | Primary Technical Proof Points | Originality & Open-Source Potential | Mandatory Cost | Solo Feasibility |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **#1** | **itch-xsk** | Market Data Ingestion, Linux High-Performance I/O & L3 Order Book | Real NASDAQ ITCH 5.0 binary decoding, MoldUDP64 framing + A/B gap recovery, recvmmsg vs. io_uring vs. AF_XDP (veth), cache-optimal intrusive L3 book, open-loop HdrHistogram tail latency. | High - few open-source repos pair real ITCH 5.0 replay with MoldUDP64 A/B loss recovery and a 3-backend Linux I/O ablation; directly relevant to libxdp/liburing ecosystems. | ₹0 | High (10-14 weeks) |
| **#2** | **shmbus-mc** | Lock-Free Concurrency, Shared-Memory IPC & Event-Sourced Sequencer | C++20 SPSC/SPMC rings, SeqLock, 128B false-sharing isolation, HugePages mmap, **GenMC bounded formal verification** (RC11/IMM), perf c2c HITM audit, Intel PT (magic-trace) tail-spike snapshots. | High - combining weak-memory formal model checking with perf c2c and Intel PT diagnostics is rare in public C++ portfolios; strong bridge to contributing tests/fixes to GenMC or HdrHistogram. | ₹0 | High (8-12 weeks) |
| **#3** | **ouch-risk-sim** | Execution Gateway (OUCH 5.0), Pre-Trade Risk & Queue-Aware Replay | Concrete constexpr OUCH 5.0 codec (avoiding template bloat), idempotent order FSM & reconciliation, AVX2 SIMD risk firewall, custom slab allocator, PGO/LTO assembly audit, queue-aware historical replay. | High - shifts focus from overdone matching engines to firm-side execution, pre-trade risk safety, compiler optimization audits, and honest microstructure simulation. | ₹0 | High (8-12 weeks) |

---

## Project 1 (Rank #1): itch-xsk - NASDAQ TotalView-ITCH 5.0 & MoldUDP64 Feed Handler, Gap-Recovery Engine, and Cache-Optimal L3 Order Book

### A. Project Identity

- **Core Mission**: A deterministic, Linux-native C++20/23 market data feed handler and full-depth Level-3 (L3) order book reconstruction engine implementing two authentic exchange wire specifications:
  - **NASDAQ MoldUDP64 v1.00**: For UDP packet framing, message sequencing, heartbeats, and gap retransmission.
  - **NASDAQ TotalView-ITCH 5.0**: For binary order-lifecycle updates.
- **Open-Loop Replayer & Benchmark Harness**: Alongside the feed handler, you build an open-loop historical packet replayer that memory-maps real multi-gigabyte NASDAQ ITCH 5.0 binary files, packs messages into compliant MoldUDP64 datagrams, injects deterministic packet drops and microbursts across a Linux virtual Ethernet (`veth`) pair, and benchmarks three swappable Linux ingestion backends (`recvmmsg` with `SO_BUSY_POLL`, `io_uring`, and `AF_XDP`) driving a zero-allocation L3 order book.
- **Production Context**: In production HFT infrastructure, the market data feed handler sits at the most latency-critical boundary between the exchange network and internal pricing models. Citadel Securities explicitly states in its Market Data Engineer specification that market data correctness, determinism, throughput, and latency directly govern trading performance and P&L, naming ITCH among core exchange protocols.
- **Real Production Problems Addressed**:
  1. Reducing kernel-to-userspace delivery overhead and tail jitter during market-open microbursts.
  2. Maintaining exact sequence integrity across duplicated A/B UDP streams when packets drop or arrive out of order.
  3. Tracking millions of live orders with minimal L1/LLC/dTLB misses and zero hot-path dynamic memory allocation.

---

### B. Why an HFT Interviewer Should Care

Inspecting `itch-xsk` allows a principal engineer to verify concrete systems skills directly in source code and profiler traces:

- **Strict Aliasing & Endianness**: Safely parsing big-endian binary protocols without undefined behavior (using `std::memcpy` / `std::bit_cast` and `std::byteswap`).
- **Fixed-Point Arithmetic**: Handling fixed-point integer prices (`Price(4)`, 4 implied decimal places, e.g. `$100.2500` stored as integer `1,000,000` rather than floating-point doubles).
- **Linux Network Stack Internals**: Understanding the Linux receive path: socket buffers, NAPI polling, ring descriptors, and eBPF XDP redirection into `AF_XDP` UMEM rings.
- **Mechanical Sympathy**: Engineering cache-sympathetic, zero-allocation data structures.
- **Amateur vs. Production Contrast**:
  - Typical student GitHub "order book" repositories almost universally synthesize CSV or in-memory random orders, store levels in `std::map<double, std::list<Order>>`, ignore wire framing and packet loss, and report a single average throughput figure.
  - In contrast, `itch-xsk` demonstrates production discipline across networking, data structures, fault recovery, and statistical latency measurement.

---

### C. Technical Architecture

The deployment model isolates two physical CPU cores (`isolcpus`, `nohz_full`, `rcu_nocbs`) on a single Linux host connected via a dedicated Linux virtual Ethernet (`veth`) pair (`veth-pub` <-> `veth-sub`):
- **Hardware Clock Synchronization**: Because both endpoints execute on the same host CPU, the replayer and feed handler read the exact same invariant hardware clock (`RDTSCP`) without cross-machine clock skew.

#### 1. Open-Loop MoldUDP64 Replayer (Core 1)
- **Memory-Mapped Ingestion**: Memory-maps a downloaded NASDAQ TotalView-ITCH 5.0 archive (`mmap` with `MADV_SEQUENTIAL`).
- **Compliant Wire Framing**: Frames variable-length ITCH messages into compliant MoldUDP64 Downstream Packets:
  - 20-byte header: `Session[10]`, `SequenceNumber[8]`, `MessageCount[2]` (where 0 signals a heartbeat and `0xFFFF` signals end of session).
  - Packed `[2-byte MessageLength][MessageData]` payload blocks.
- **Pacing & Burst Simulation**: Supports constant-rate open-loop pacing (eliminating coordinated omission) alongside time-compressed historical burst replay (replaying real market-open bursts at 1x, 5x, or 10x speed).
- **Benchmarking & A/B Injection**: Embeds a transmit `RDTSCP` cycle stamp, duplicates traffic across Feed A and Feed B streams over Linux `veth` pairs, injects configurable packet drops or reorderings, and runs a MoldUDP64 retransmission responder serving Request packets.

#### 2. Swappable Linux Networking Backends (Core 2)
Three ingress engines sit behind a compile-time C++20 concept policy, eliminating virtual dispatch overhead on the packet-receive loop:
- **Backend A (`recvmmsg` + `SO_BUSY_POLL`)**: Amortizes syscall transitions across batches while still traversing the full kernel `sk_buff` -> IP -> UDP -> socket queue chain.
- **Backend B (`io_uring`)**: Leverages shared submission and completion rings with registered fixed buffers to evaluate asynchronous kernel I/O against busy-polled sockets.
- **Backend C (`AF_XDP` + eBPF)**: Attaches a minimal eBPF XDP filter to the `veth` interface that checks UDP destination ports and calls `XDP_REDIRECT` into an AF_XDP socket (`XSK`) backed by four shared-memory rings (Fill, RX, TX, Completion) and fixed-frame UMEM.
- **Zero-Copy Path**: On `veth`, AF_XDP operates in copy mode at ₹0; on an optional desktop Intel NIC supporting `igc` or `ixgbe`, the identical userspace ring code switches directly to zero-copy DMA.

#### 3. A/B Arbitrator, Gap Recovery, and Branchless ITCH 5.0 Decoder
- **Sequence Tracking**: The arbitrator tracks `next_expected_seq`.
  - Whichever redundant feed delivers `seq == next_expected_seq` first immediately advances the decoder.
  - Trailing duplicates (`seq < next_expected_seq`) drop in $O(1)$.
- **Gap Recovery**: When both feeds drop a packet (`seq > next_expected_seq`), incoming future packets stage inside a pre-allocated out-of-order ring buffer while a MoldUDP64 Request Packet (`Session[10]`, `FirstSeq[8]`, `RequestedMessageCount[2]`) requests retransmission from the replay server.
- **Supported Messages**: Validated payloads enter a branchless ITCH 5.0 decoder supporting core order-lifecycle and market-state messages:
  - System Event (`S`), Stock Directory (`R`)
  - Add Order (`A`), Add Order with MPID (`F`)
  - Order Executed (`E`), Order Executed with Price (`C`)
  - Order Cancel (`X`), Order Delete (`D`), Order Replace (`U`)
  - Trade (`P`), Cross Trade (`Q`), Net Order Imbalance Indicator (`I`)
- **Branchless Byte Conversion**: Byte-order conversion relies on `std::byteswap` (C++23) or `__builtin_bswap64`, dispatched via a flat table indexed by message-type byte to minimize indirect branch mispredictions.

#### 4. Cache-Optimal L3 Order Book, Memory Strategy, and OS Tuning
- **Zero Allocation on Hot Path**: All hot-path state lives in pre-allocated contiguous memory backed by `mmap` with 2 MiB HugePages (`MAP_HUGETLB` or `MADV_HUGEPAGE`) and locked via `mlockall(MCL_CURRENT | MCL_FUTURE)` to eliminate runtime page faults and shrink dTLB pressure.
- **Intrusive 64-Byte Cache-Line Layout**: Each `OrderNode` fits inside a single 64-byte cache line and uses 32-bit slab indices (halving pointer footprint relative to 64-bit raw pointers) for intrusive doubly-linked FIFO queues within each price level.
- **Flat Open-Addressing Hash Map**: Order lookups by 64-bit `OrderReferenceNumber` run through a pre-sized, power-of-2 open-addressing flat hash map (linear or Robin-Hood probing with backward-shift deletion to avoid tombstone accumulation during long sessions).
- **Hybrid Dense BBO Tick Array**: Price levels per symbol use a hybrid dense tick-array anchored around the active Best Bid/Offer (BBO) with a sparse overflow map for deep far-from-market quotes, paired with a compact bitset scanned via `std::countl_zero` / `TZCNT` to locate the next active best price level in $O(1)$.
- **Thread Pinning & Core Isolation**: The feed-handler thread executes strictly single-threaded (no mutexes, no locks, no dynamic allocation) pinned to an isolated physical core (`pthread_setaffinity_np`) with SMT disabled or sibling cores left idle.

---

### D. Implementation Roadmap

| Milestone | What to Implement | Concepts to Master First | Completion Criteria | Verification & Tests | Dependencies |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **M1: Offline ITCH 5.0 Parser & Validator** | Zero-copy mmap file reader, big-endian decoder for core ITCH 5.0 messages, symbol directory lookup. | Binary wire protocols, endianness, C++ strict aliasing, std::bit_cast, fixed-point Price(4) arithmetic. | Parses a full 3.5 GB+ historical NASDAQ ITCH 5.0 file with zero sanitizer errors and accurate message histograms. | Verify downloaded archive .md5sum integrity, check intra-day timestamp monotonicity, and run under ASan + UBSan. | None (Start here). |
| **M2: Naive Baseline vs. Cache-Optimal L3 Book** | Build Baseline 1 (std::map + std::unordered_map) and Optimized 1 (HugePage intrusive slab pool + flat hash map + dense BBO tick array). | Cache lines, false sharing, intrusive containers, backward-shift deletion, std::countl_zero. | In-process replay microbenchmark shows >= 3x tick-to-book throughput delta and zero heap allocations. | Differential replay test: assert identical best bids/offers and volume across all ticks. | M1. |
| **M3: MoldUDP64 Packetizer, A/B Arbitrator & Gap Recovery** | MoldUDP64 v1.00 encoder/decoder, open-loop pacing replayer, A/B feed arbitrator, gap-detection state machine, Request/Retransmit loop. | UDP packet framing, coordinated omission, sliding-window sequence tracking, out-of-order reassembly buffers. | Correctly processes 10M messages with 1% injected packet loss across A/B feeds without dropping state or deadlocking. | Chaos unit tests injecting duplicate packets, out-of-order delivery, and retransmission timeouts. | M1, M2. |
| **M4: Swappable Linux I/O Backends (recvmmsg, io_uring, AF_XDP)** | Implement all three backends across Linux veth pair: recvmmsg + SO_BUSY_POLL, io_uring fixed-buffer polling, AF_XDP copy-mode UMEM rings. | Linux networking stack, NAPI poll, eBPF XDP programs, AF_XDP UMEM rings, veth setup. | Sustains >= 1.5M msgs/sec throughput across veth pair; AF_XDP demonstrates lowest kernel-to-userspace overhead. | Loopback packet-drop test, UMEM ring-overflow asserts, libbpf verification. | M3. |
| **M5: Telemetry, Hardware Counters & Profiling Suite** | Open-loop HdrHistogram collector, RDTSCP cycle-to-ns timing, Linux perf stat automation script, perf c2c cache-line audit. | Tail latency percentiles (p50/p90/p99/p99.9), PMU hardware counters, LLC/dTLB miss profiling. | Produces full 2x3 ablation report (Naive vs. Optimal Book x recvmmsg/io_uring/AF_XDP) with hardware-counter diffs. | Validate cycle-invariant RDTSCP conversion, confirm nohz_full isolation, eliminate benchmark harness jitter. | M4. |

---

### E. Benchmarking and Validation Plan

#### 1. Avoiding Coordinated Omission in Tail-Latency Benchmarking
- **The Flaw of Averages**: A pervasive flaw in amateur low-latency benchmarks is reporting averages or quiet-period medians, or using a closed-loop harness where the sender pauses while waiting for the receiver (coordinated omission).
- **Microburst Reality**: Real trading systems fail during microbursts. An industry latency engineering analysis of the U.S. Options Price Reporting Authority (OPRA) multicast expansion illustrates why median metrics are deceptive: expanding from 48 to 96 multicast lines barely budged P50 median latency, yet collapsed P99 tail latency by nearly 90%.

#### 2. Correctness, Stress Testing, and Ablation Methodology
- **Differential Golden Replay**: Validate book correctness by differentially replaying a complete trading day of authentic NASDAQ ITCH 5.0 binary data (such as `12302019.NASDAQ_ITCH50.gz` ~3.52 GB compressed, or `01302020.NASDAQ_ITCH50.gz` ~5.60 GB compressed) through both the reference `std::map` book and your optimized slab book, asserting identical L1/L2 snapshots and volume invariants on every update.
- **Packet-Loss Convergence**: Follow this with a bursty packet-loss stress test injecting 1% packet drops and reordering across A/B feeds to prove exact convergence.
- **2x3 Ablation Matrix**: Execute a strict 2x3 ablation matrix comparing:
  - *(Naive `std::map` Book vs. Cache-Optimal L3 Book)* across
  - *(`recvmmsg` + busy-poll vs. `io_uring` vs. `AF_XDP` copy mode)*.
- **In-Process Microbenchmark**: Pair with an in-process decode-plus-book microbenchmark separating CPU/cache improvements from kernel networking latency.

#### 3. Latency, Throughput, and Hardware-Counter Profiling
- **Open-Loop Load Driving**: Drive the benchmark using an open-loop load generator stepping throughput through distinct levels (100k, 500k, 1M, and 2M msgs/sec up to peak sustainable msgs/sec), recording every latency sample into Gil Tene's `HdrHistogram`.
- **Tail Latency Reporting**: Extract $p50$, $p90$, $p99$, and $p99.9$ wire-to-book latency distributions.
- **PMU Hardware Counters**: Profile hardware counters via Linux `perf stat -e`:
  - `cycles`, `instructions`, `IPC`
  - `L1-dcache-load-misses`, `LLC-load-misses`
  - `dTLB-load-misses`
  - `branch-misses`
- **Cache Contention**: Audit cache-line bouncing with `perf c2c` to prove that book updates avoid false sharing.

#### 4. Consumer Hardware Validity Boundaries
Document explicitly in your README which measurements are physically valid on consumer hardware:
- **Valid on Standard PC**: Relative deltas between `std::map` and flat slab pools, `TZCNT` bitset vs. map iteration, and L1/LLC miss reductions are 100% physically valid.
- **Acknowledging Hardware Ceilings**: Acknowledge honestly that `AF_XDP` on `veth` measures Linux kernel bypass software architecture, not physical PCIe NIC DMA transfer latencies (which require enterprise NICs like Solarflare / Mellanox).

---

### F. Hardware and Financial Cost (INR)

- **Mandatory Cost (₹0)**: All code compiles and benchmarks on a standard Linux PC, laptop, or dual-boot system using Linux `veth` virtual Ethernet pairs, in-memory packet replay, and open-source verification tooling.
- **Optional Desktop-Only Upgrade (₹4,799 - ₹10,439)**: Solely if you have a free desktop PCIe slot and wish to measure physical kernel-bypass NIC behavior:
  - **Single-port 2.5GbE Intel I225-V / I226-V**: ~₹2,099.
  - **Dual-Port 2.5GbE Intel I225-T1 / I226**: Listed at **₹4,799 - ₹5,000**.
  - **Dual-Port 10GbE SFP+ Intel X520-DA2 (82599ES)**: Listed at **₹8,599 - ₹10,439** (requiring an inexpensive Cat6/SFP+ DAC cable).
- **Physical Kernel-Bypass Caveat**: Enables real physical zero-copy DMA (`igc` / `ixgbe`). Zero-copy `AF_XDP` requires driver-level support (`igc`, `ixgbe`, `i40e`, `ice`, or NVIDIA `mlx5`); buying a generic ₹400 PCIe Realtek NIC will fail because Realtek drivers lack AF_XDP zero-copy UMEM hooks.
- **Free Baseline Parity**: Running `AF_XDP` across Linux `veth` in copy mode teaches 100% of the software architecture for **₹0**.

---

### G. Resume Impact and Interview Preparation

#### Technically Accurate Resume Bullet
- Engineered a C++23 NASDAQ TotalView-ITCH 5.0 / MoldUDP64 feed handler and L3 order book with A/B gap recovery and swappable `recvmmsg` / `io_uring` / `AF_XDP` Linux I/O backends; replaced `std::map` / heap nodes with HugePage-backed intrusive slabs and flat open-addressing indices, cutting p99.9 tick-to-book latency by X% and LLC/dTLB misses by Y%/Z% across N million replayed historical messages (`perf stat`, open-loop `HdrHistogram`).

#### Required Measurable Evidence Before Using This Bullet
- Committed reproducible benchmark scripts.
- Full CPU/kernel/compiler configuration disclosure (`isolcpus`, `nohz_full`, `rcu_nocbs`).
- Raw HdrHistogram p50/p90/p99/p99.9 distributions over isolated worst-burst windows.
- `perf stat` counter diffs and a passing Golden Differential Test over tens of millions of real ITCH messages.

#### High-Signal Technical Interview Questions
- How does your flat open-addressing hash map prevent lookup degradation over a full trading day when the vast majority of resting orders are canceled?
- Why did you use 32-bit slab indices rather than 64-bit pointers?
- Trace a UDP datagram step-by-step through Linux `recvmmsg` versus eBPF `XDP_REDIRECT` into an AF_XDP UMEM ring.

#### Difficult Follow-Up Questions
- What happens to your dense BBO tick-array when a symbol halts, undergoes a reverse split, or receives deep off-market quotes thousands of ticks away from the mid-price?
- How does your MoldUDP64 state machine handle a dropped retransmission response while live multicast sequence numbers keep advancing?
- Why can AF_XDP or `SO_BUSY_POLL` degrade latency if RSS queue steering or NIC interrupt coalescing (`ethtool -C rx-usecs`) is misconfigured?

---

### H. GitHub Presentation

Organize the repository cleanly:
- `include/itch_xsk/` (`protocol/`, `net/`, `book/`, `telemetry/`)
- `src/`
- `examples/`
- `benchmarks/`
- `tests/`
- `scripts/` (for CPU isolation, hugepage setup, and `veth` creation)

Include a root `README.md` featuring:
- An ASCII architecture diagram of the dual-core pipeline.
- Markdown comparison tables of the 2x3 ablation results.
- Rendered SVG tail-latency graphs plotted with `matplotlib` from raw HdrHistogram CSVs.
- Clear reproduction steps (`cmake -B build -DCMAKE_BUILD_TYPE=Release && cmake --build build`).

---

## Project 2 (Rank #2): shmbus-mc - Formally Verified Lock-Free Shared-Memory IPC, Event-Sourced Sequencer, and Hardware-Traced Telemetry Engine

### A. Project Identity

- **Core Mission**: A C++20/23 ultra-low-latency inter-process communication (IPC) library and deterministic event-sourced sequencer engineered for high-throughput, microsecond-critical trading pipeline stages.
- **Verification & Observability Stack**: What elevates `shmbus-mc` into rare territory is its rigorous verification and observability stack:
  - Every lock-free atomic path is **exhaustively bounded-model-checked under weak memory models (RC11 and IMM) using GenMC**.
  - Audited for cross-core MESI cache-line transfers with **Linux `perf c2c`**.
  - Instrumented with a cold-path **Intel Processor Trace (`magic-trace`) / AMD IBS** snapshot trigger that captures ~30 ns hardware execution timelines whenever a p99.9 tail-latency spike breaches threshold.
- **Production Context**: In real HFT systems, firms avoid mutex contention on the hot path by isolating single-threaded stages (feed handler -> strategy -> risk gateway -> logger) communicating over lock-free shared-memory rings and a deterministic sequencer. Citadel Securities, Optiver, and Jane Street repeatedly stress determinism, replayability, and hardware-level latency tracing in their engineering discussions.

---

### B. Why an HFT Interviewer Should Care

Lock-free concurrency and C++ atomic memory orderings are among the sharpest technical filters in HFT interviews-and the domain where surface-level candidates are exposed fastest:

- **The x86-64 TSO Trap**: Because x86-64 hardware enforces Total Store Order (TSO), a subtly broken C++ ring buffer using `memory_order_relaxed` where acquire/release is required will frequently survive millions of stress-test iterations without failing, only to break under aggressive compiler reordering or weak-memory ARM64 CPUs.
- **Formal Verification with GenMC**: By compiling your C++20 synchronization primitives via Clang to LLVM IR and verifying bounded multi-threaded clients exhaustively under **RC11 and IMM with GenMC**, you provide rigorous verification against weak-memory ordering bugs and data races.
- **Cache-Line False Sharing & HITM**: Pairing that formal audit with `perf c2c` HITM (Hit in Modified state) cache-contention measurements-proving why 64-byte alignment can still trigger false sharing under 128-byte spatial cache prefetching-and `magic-trace` root-cause captures of actual OS jitter demonstrates principal-level systems mastery.

---

### C. Technical Architecture

`shmbus-mc` is structured into two strictly decoupled planes:
- **Runtime Shared-Memory IPC Plane**:
  - Core 1 hosts the Producer and Deterministic Sequencer writing into a single HugePage-backed shared-memory region subdivided into three physically separated cache-isolated zones: a 128-byte-padded Write Cursor strip, a 128-byte-padded Read Cursors strip, and a power-of-two contiguous Data Slot Array.
  - Core 2 runs an SPMC Strategy Reader pinned to an isolated core and hooked to a cold-path hardware execution tracing tail-latency trigger.
  - Core 3 runs an asynchronous Journal Writer draining the same shared-memory ring into an append-only binary replay log.
- **Formal Verification & Contention Audit Plane**:
  - The exact same C++20 atomic ring headers are compiled through Clang to LLVM IR and fed into the GenMC verifier under RC11 and IMM memory models.
  - Cross-core stress loads are profiled continuously with `perf c2c` and `HdrHistogram`.

#### 1. Wait-Free SPSC Ring Buffer (`SpscRing<T>`)
- **Power-of-2 Indexing**: Enforces power-of-2 capacity (`index & (N - 1)`) and `static_assert(std::is_trivially_copyable_v<T>)` so cross-process shared-memory transport remains free of object-lifetime or vtable pointer corruption.
- **128-Byte False-Sharing Padding**: Following Erik Rigtorp's ring-buffer optimizations, `write_idx_` and `read_idx_` sit on distinct **128-byte aligned boundaries** (`alignas(128)`) to neutralize adjacent-cache-line prefetching false sharing.
- **Peer Cursor Caching**: Each endpoint maintains a thread-local cached copy of the peer's cursor (`cached_read_idx_` on producer, `cached_write_idx_` on consumer), issuing an acquire atomic load of the shared cursor only when its local cached bound appears full or empty-sharply reducing cross-core cache invalidations.
- **Minimal C++20 Atomics**: All hot-path operations use minimal C++20 orderings (relaxed for self-index loads, release for publishing writes/reads, acquire for observing remote progress) and never `memory_order_seq_cst`.

#### 2. SPMC Broadcast Ring, SeqLock, and Event-Sourced Sequencer
- **Multi-Consumer SPMC Policies**: `SpmcRing<T>` supports multiple independent processes mapped into the shared segment under two policies:
  - *Backpressure Mode*: Producer throttles to the slowest active consumer cursor for lossless journaling and risk stages.
  - *Overwrite/Epoch Mode*: Monotonic 64-bit sequence tag per slot enabling slow market-data consumers to detect wrap-around and resynchronize cleanly.
- **UB-Free SeqLock (`SeqLock<T>`)**: Provides wait-free single-writer, multi-reader publication of latest BBO or risk parameters via odd/even version counters and chunked atomic payload loads with `std::atomic_thread_fence` ordering-offering an ideal second target for GenMC verification.
- **Deterministic Sequencer**: Assigns strictly monotonic 64-bit sequence numbers and `RDTSCP` timestamps to every inbound command.
- **Asynchronous Journal Writer**: Persists committed records in batches off the critical path (`O_DIRECT` or `mmap` flush) so any crashed downstream engine rebuilds bit-for-bit identical state strictly by replaying the input log.

#### 3. HugePage/NUMA Memory Strategy and Hardware Diagnostics
- **HugePage Allocation**: Shared-memory segments are backed by `shm_open` or `memfd_create` with 2 MiB HugePages (`hugetlbfs`) and locked via `mlock` to eliminate page-table walk overhead and avoid runtime TLB misses.
- **Contention Auditing**: In benchmark mode, a background telemetry harness triggers `perf c2c record` under multi-producer and multi-consumer loads, quantifying local and remote HITM (Hit in Modified cache line) cycles across progressive padding states (0B, 64B, 128B).
- **Tail-Spike Postmortem Trigger**: A dedicated cold-path tail-spike monitor tracks latency via RDTSCP; whenever a ping-pong transfer exceeds a pre-set threshold (e.g., 5 microseconds), it signals a hardware execution tracing snapshot trigger (Intel PT / `magic-trace` on Intel, or `perf script` / AMD IBS on AMD), providing microsecond-by-microsecond assembly execution proof of why the tail spike occurred (such as OS interrupt, page fault, or cache invalidation).

---

### D. Implementation Roadmap

| Milestone | What to Implement | Concepts to Master First | Completion Criteria | Verification & Tests | Dependencies |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **M1: Baseline Mutex Queue vs. Progressive SpscRing** | Build four variants: std::mutex queue, unpadded seq_cst ring, 64B-padded acquire/release ring, 128B-padded cached-cursor ring. | C++ memory orderings (relaxed, acquire, release), cache line bouncing, false sharing, alignas. | 128B cached-cursor variant achieves >= 4x throughput and lowest p99.9 latency over mutex baseline. | ThreadSanitizer clean; unit tests asserting FIFO order across 50M transfers. | None. |
| **M2: GenMC Bounded Formal Verification Suite** | Install GenMC; write bounded LLVM-IR verification harnesses for SpscRing, SpmcRing, and SeqLock under --rc11 and --imm. | Axiomatic weak memory models (RC11, IMM), LLVM IR compilation with Clang, bounded model checking. | GenMC reports 0 data races, 0 assertion failures, and 0 memory leaks across all explored thread interleavings. | Inject an intentional relaxed bug; verify GenMC catches it and generates a counterexample graph (.dot). | M1. |
| **M3: SPMC Broadcast Ring, SeqLock & Event-Sourced Sequencer** | Implement multi-consumer SPMC ring (backpressure + overwrite modes), SeqLock<T>, monotonic 64-bit sequencer, and binary crash-replay journal. | Readers-writer synchronization, sequence wrapping, event sourcing, crash recovery determinism. | Crashed consumer rebuilds 100% bit-identical state from journal; SeqLock survives heavy concurrent reader stress. | Chaos test: kill -9 consumers mid-stream and assert deterministic state reconstruction. | M1, M2. |
| **M4: perf c2c Contention & Open-Loop Ping-Pong Suite** | Build cross-core ping-pong RTT and stepped-rate open-loop harnesses with HdrHistogram; run perf c2c to quantify HITM. | Linux perf c2c, MESI protocol states (Shared, Exclusive, Modified), spatial prefetcher false sharing. | Documented table proving 128B padding collapses HITM counts by >= 90% compared to 0B/64B padding under prefetching. | perf c2c report showing 0 high-cost remote HITM events on the 128B-padded ring. | M3. |
| **M5: Intel PT (magic-trace) Tail-Spike Postmortem** | Wire magic-trace snapshot hook on tail-latency breach (> 5 us); record and symbolize hardware execution trace leading into the spike. | Intel Processor Trace, hardware branch packets, symbol decoding, OS jitter root-causing. | Generates interactive Perfetto flamegraph / trace view isolating the exact assembly instructions causing the tail spike. | Force a spike via artificial core migration or memory thrash; verify trace isolates the exact interrupt/preemption. | M4. |

---

### E. Benchmarking and Validation Plan

#### 1. Correctness and Bounded Formal Verification
- **Formal Model Checking**: Combine standard unit tests and TSan with **GenMC exhaustive bounded stateless model checking** under RC11 and IMM.
- **TSan Limits on x86**: Complement formal verification with ThreadSanitizer in CI, documenting in your write-up why TSan alone cannot prove lock-free correctness on x86-64 hardware because TSan validates executions under the host's actual memory model (TSO) rather than all executions permitted by the C++ abstract machine.
- **Chaos Kill Testing**: Conduct crash-resilience testing by injecting `kill -9` signals into active consumer processes and asserting that the replay sequencer re-establishes bit-for-bit identical state from the binary journal.

#### 2. Baselines, Latency, Throughput, and Contention Analysis
- **Five Progressive Variants**: Benchmark all five progressive variants:
  1. `std::mutex` + `std::queue`
  2. Unpadded atomic ring with `memory_order_seq_cst`
  3. 64B-padded ring with `memory_order_seq_cst`
  4. 64B-padded ring with acquire/release
  5. 128B-padded ring with acquire/release and local cursor caching
- **Metrics Collected**: Run both a ping-pong round-trip latency harness (logging $p50$, $p90$, $p99$, and $p99.9$) and a stepped-rate open-loop throughput harness up to near-saturation.
- **`perf c2c` Audit**: Execute `perf c2c record --call-graph dwarf` on both unpadded and padded variants to produce an unambiguous HITM reduction table proving why adjacent cache-line prefetching mandates 128-byte spacing.

#### 3. Tail-Spike Root-Cause Tracing
- **Microarchitectural Postmortem**: Wire a tail-latency trigger into `shmbus-mc`. When ping-pong RTT exceeds a threshold, dump an execution trace via Intel PT (`magic-trace`) or AMD IBS.
- **Trace Inspection**: Inspect the trace in the Perfetto web viewer to identify the exact instruction-level cause: whether an OS tick interrupt (`CONFIG_NO_HZ_FULL` misconfiguration), an unexpected page fault, or CPU frequency scaling.

#### 4. Consumer Hardware Validity Boundaries
- **Valid on Standard PC**: Cross-core cache coherence, L1/L2/L3 transfer costs, 64B vs. 128B false sharing, and atomic acquire/release synchronization are physical CPU properties that behave identically on consumer desktops and multi-socket server hardware.
- **Cloud VM Pitfall**: Acknowledge that running `magic-trace` requires bare-metal Linux hardware execution tracing support (not a cloud VM without PT / PMU virtualization passthrough).

---

### F. Hardware and Financial Cost (INR)

- **Mandatory Cost (₹0)**: Zero additional expenditure required. Every component, benchmark, and formal verification script runs on an existing Linux PC or dual-boot workstation.
- **Optional Cost (₹0)**: Zero physical upgrades required.
- **All Tooling Open Source**: GenMC, Linux `perf`, `magic-trace`, Clang, and `HdrHistogram` are free and open-source.

---

### G. Resume Impact and Interview Preparation

#### Technically Accurate Resume Bullet
- Built a C++20 lock-free shared-memory IPC library (SPSC/SPMC rings, SeqLock, event-sourced binary sequencer) backed by 2 MiB HugePages; verified bounded atomic correctness under RC11/IMM weak memory models with GenMC and eliminated false-sharing HITM stalls (`perf c2c`), reducing cross-core p99.9 latency by X% over unpadded `seq_cst` baselines.

#### Required Measurable Evidence Before Using This Bullet
- Clean GenMC verification logs under both RC11 and IMM.
- An archived DOT counterexample graph for an injected weak-ordering bug.
- Before-and-after `perf c2c` HITM tables.
- `HdrHistogram` ping-pong plus open-loop latency tables on isolated cores.

#### High-Signal Technical Interview Questions
- Why can `SpscRing` safely use `memory_order_relaxed` on self-cursor loads, and what exact interleaving breaks if the producer downgrades its store from release to relaxed?
- Why align cursors to 128 bytes rather than 64 bytes?
- How does `SpscRing` remote-index caching reduce MESI bus traffic?

#### Difficult Follow-Up Questions
- Under the C++20 abstract machine, reading non-atomic payload bytes concurrently with a SeqLock writer is formally a data race (UB) even if torn reads are discarded: how do you eliminate UB using chunked `std::atomic` relaxed accesses and fences?
- What happens in your SPMC overwrite ring if OS preemption stalls a reader long enough for the ring buffer to lap it?
- What documented interaction between Linux `nohz_full` and CPU power management drivers can cause unexpected frequency/C-state slowdowns, and how does `rcu_nocbs` help mitigate it?

---

### H. GitHub Presentation

Package the project cleanly as a CMake library:
- `include/shmbus/` (`spsc_ring.hpp`, `spmc_ring.hpp`, `seqlock.hpp`, `sequencer.hpp`)
- `src/sequencer/`
- `verify/genmc/` (LLVM IR harness scripts, verified test outputs)
- `benchmarks/` (`ping_pong/`, `open_loop/`, `contention_c2c/`)
- `telemetry/` (`magic_trace_hooks/`)

Include a root `README.md` featuring:
- An ASCII memory layout diagram illustrating 128-byte false-sharing isolation.
- Embedded GenMC counterexample DOT graphs showing a caught weak-memory race.
- A Markdown table showing HITM counts collapsing from hundreds to zero via 128-byte padding.
- One-line reproduction commands (`genmc --rc11 -I include verify/genmc/verify_spsc.c`).

---

## Project 3 (Rank #3): ouch-risk-sim - Compile-Time OUCH 5.0 Execution Gateway, SIMD Pre-Trade Risk Firewall, and Queue-Aware Historical Replay Engine

### A. Project Identity

- **Core Mission**: An outbound order-execution gateway, pre-trade risk firewall, and deterministic queue-aware historical replay engine engineered to bridge the gap between core systems infrastructure and quantitative execution logic.
- **Production Context**: In production HFT firms, a single buggy order state transition or bypassed pre-trade risk check can cause catastrophic financial losses in milliseconds (as Knight Capital proved). Citadel Securities explicitly highlights the necessity of deterministic state machines, failure idempotency, and compile-time correctness in its order execution pipelines.
- **Core Components**:
  1. Compile-time (`constexpr`) NASDAQ OUCH 5.0 protocol codec.
  2. Idempotent order state machine with state-space exhaustion testing.
  3. AVX2 SIMD pre-trade risk firewall.
  4. Queue-aware historical exchange simulator modeling matching-engine latency and queue priority.

---

### B. Why an HFT Interviewer Should Care

Inspecting `ouch-risk-sim` allows interviewers to verify four high-signal competencies rarely seen together in junior repositories:

1. **Compile-Time Engineering**: Mastering compile-time C++ without incurring massive template bloat (a direct reflection of Herb Sutter's and Citadel's production guidance).
2. **SIMD Vectorization**: Vectorizing numerical validation using AVX2 SIMD intrinsics and auditing generated assembly.
3. **Resilient Concurrency & State Machines**: Modeling asynchronous order lifecycles and race conditions (e.g. fill reports arriving while a cancel request is in flight).
4. **Market Microstructure Sympathy**: Simulating exchange matching mechanics with realistic FIFO queue priority and adverse selection rather than assuming naive instant fills.

---

### C. Technical Architecture

The execution gateway and historical simulator share a single deterministic event interface so identical risk, state-machine, and codec code runs identically in both live and historical backtest modes.

#### 1. Compile-Time (`constexpr`) OUCH 5.0 Codec
- **Protocol Support**: Encodes and decodes NASDAQ OUCH 5.0 variable-length binary messages:
  - Enter Order (`O`), Replace Order (`U`), Cancel Order (`X`)
  - Order Accepted (`A`), Order Replaced (`U`), Order Canceled (`C`), Order Executed (`E`), Broken Trade (`B`)
- **Zero-Allocation Descriptors**: Uses concrete fixed-layout structs with fixed-point arithmetic (`Price(4)`) and zero dynamic memory allocation.
- **Compile-Time Wire Offsets**: Employs `constexpr` parsing logic where field offsets and message validation rules evaluate at compile time.
- **Avoiding Template Bloat**: In alignment with Citadel's production engineering practices, avoids Alexandrescu-style template parameter bloat, keeping compilation times low and measuring compiler instantiation overhead via Clang `-ftime-trace`.

#### 2. AVX2 SIMD Pre-Trade Risk Firewall
- **Structure-of-Arrays (SoA) Layout**: Maintains trading limits for all registered symbols in contiguous Structure-of-Arrays (SoA) tables:
  - `net_position[symbol]`
  - `pending_open_buy_qty[symbol]`, `pending_open_sell_qty[symbol]`
  - `max_position_limit[symbol]`, `max_order_qty[symbol]`, `max_order_notional[symbol]`
- **Vectorized Limit Checks**: When a new order arrives, checks all safety limits simultaneously using AVX2 intrinsics (`_mm256_cmpgt_epi64` + `_mm256_movemask_epi8`), with an optional AVX-512 fallback for architectures like AMD Zen 5.
- **Sub-5 ns Firewall**: Evaluates position limits, fat-finger checks, price bands, and credit limits in under 5 nanoseconds, producing a binary allow/reject decision with zero branch mispredictions on the valid path.

#### 3. Custom Slab Allocator and Idempotent Order FSM
- **Zero Heap Allocations**: Active `OrderSlot` records reside inside a pre-allocated contiguous slab with an intrusive $O(1)$ freelist.
- **Exhaustive State x Event FSM**: The order state machine models the complete lifecycle:
  - `NewPending`, `Active`, `CancelPending`, `ReplacePending`, `Filled`, `Canceled`, `Rejected`
- **Race Condition Handling**: Handles asynchronous execution events cleanly:
  - Fill arrives while Cancel is pending.
  - Cancel arrives after full fill.
  - Replaced confirmation arrives out of sequence.
- **Disconnect Reconciliation**: Simulates network drops and recovers state via OUCH sequence reconciliation.

#### 4. Queue-Aware Historical Exchange Simulator (Market Realism)
- **Beyond Naive Fills**: Rather than assuming instant fills at the historical touch price, the simulator reads real NASDAQ ITCH 5.0 order-book events and tracks your order's exact position in the FIFO queue at each price level.
- **Deterministic Latency Wheel**: Uses a deterministic timing-wheel latency injector modeling:
  - Wire latency (e.g. 5 microseconds).
  - Exchange matching engine queuing latency (with microburst spikes).
- **Adverse Selection Modeling**: Accurately reproduces queue cancellation dynamics (cancelling at tail of queue vs. front of queue) and proves why latency degradation leads directly to adverse selection (fills occur mostly when market moves against you).

---

### D. Implementation Roadmap

| Milestone | What to Implement | Concepts to Master First | Completion Criteria | Verification & Tests | Dependencies |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **M1: constexpr OUCH 5.0 Codec & Compile-Time Audit** | Variable-length OUCH 5.0 encoder/decoder, UserRefNum framing, optional tag parser; benchmark concrete constexpr vs. policy-templated variant. | OUCH 5.0 binary spec, constexpr evaluation, Clang -ftime-trace template instantiation analysis. | Round-trip fuzz-tested codec with zero UB; documented compile-time and binary-size comparison table. | Property-based round-trip fuzzing (encode -> decode -> byte-identical) under ASan/UBSan. | None. |
| **M2: Custom Slab Allocator & Idempotent Order FSM** | Pre-allocated contiguous slab allocator with O(1) freelist, dense order-token map, full lifecycle FSM, and state-transition validator. | Intrusive freelists, deterministic state machines, asynchronous race reconciliation, crash replay. | Passes an exhaustive 8x12 State x Event transition matrix test with zero invalid transitions or memory leaks. | State-machine chaos tester injecting out-of-order execution reports and duplicate cancels. | M1. |
| **M3: Scalar vs. AVX2 SIMD Risk Firewall** | Implement SoA limit tables, scalar reference checker, AVX2 SIMD vectorized checker (_mm256_cmpgt_epi64), and branchless allow/reject mask. | SIMD vectorization, SoA vs. AoS, alignment (alignas(32)), AVX-512 comparison on Zen 5/x86. | AVX2 risk check completes in < 5 ns; assembly inspection confirms zero scalar spills on the hot path. | Differential fuzz test asserting 100% identical allow/reject decisions between Scalar and AVX2 across 50M random orders. | M1, M2. |
| **M4: Static vs. Virtual Dispatch & PGO/LTO Compiler Study** | Benchmark virtual-interface gateway vs. CRTP/concrete gateway; apply -O3, -flto, and Profile-Guided Optimization (PGO); audit assembly. | Devirtualization, vptr/vtable cache overhead, Clang PGO pipeline, LTO cross-module inlining. | Produces a clean benchmark table and annotated assembly dump proving cycle drops from devirtualization and PGO. | Assembly diffs confirming inlined hot paths and branch-prediction hint alignment. | M2, M3. |
| **M5: Queue-Aware Historical Replay Engine** | Build deterministic timing-wheel latency injector, FIFO queue-depth tracker using ITCH L3 events, and adverse-selection analytics engine. | Exchange microstructure, FIFO matching priority, queue positioning, adverse selection, markouts. | Simulates realistic execution fills; demonstrates that adding 10 us latency worsens fill quality and markout P&L. | Replay validation: verify simulated fill prices match historical trade prints and volume bounds. | M3, M4, and itch-xsk L3 output. |

---

### E. Benchmarking and Validation Plan

#### 1. Correctness and Edge-Case Validation
- **Exhaustive State x Event Matrix**: Verify the order FSM against an exhaustive 8x12 State x Event transition matrix covering every legal and illegal transition.
- **Differential Fuzzing**: Perform differential fuzz testing between the AVX2 SIMD risk checker and the scalar reference implementation across 50 million randomized orders to prove identical allow/reject decisions under all edge cases.

#### 2. Ablations, Cache-Cold Profiling, and Hardware Counters
Measure four targeted ablations:
1. `std::vector` dynamic allocation vs. Custom Slab Pool with intrusive freelist.
2. Virtual dispatch (`vtable` indirection) vs. Concrete/Static dispatch.
3. Scalar vs. AVX2 Structure-of-Arrays (SoA) limit checks.
4. `-O3` baseline vs. `-O3 -flto` vs. Clang Profile-Guided Optimization (PGO).

Profile both:
- **Cache-Hot Latency**: Microbenchmark loop latency.
- **Cache-Cold Latency**: Flush caches with `_mm_clflush` before execution to simulate realistic, sporadic trade signals.
- **Hardware PMU Counters**: Collect `perf stat` data tracking `instructions`, `cycles`, `branch-misses`, and `L1-icache-load-misses`.

#### 3. Consumer Hardware and Financial Realism Boundaries
- **Valid on Standard PC**: Instruction counts, branch-miss reductions, cache-cold behavior, and compiler optimizations are 100% valid on a consumer PC.
- **Microstructure Realism**: Acknowledge that the queue-aware simulator models exchange matching mechanics under deterministic assumptions, not live exchange matching engine state.

---

### F. Hardware and Financial Cost (INR)

- **Mandatory Cost (₹0)**: Zero additional spending required.
- **Optional Cost (₹0)**: Zero physical upgrades required.
- **Architecture Note**: AVX2 is supported on all modern x86-64 CPUs (Intel Haswell+, AMD Zen 1+). On AMD Zen 5 (e.g. Ryzen 7 9700X), an optional AVX-512 code path can be added with zero downclocking penalty.

---

### G. Resume Impact and Interview Preparation

#### Technically Accurate Resume Bullet
- Architected a zero-allocation C++23 NASDAQ OUCH 5.0 execution gateway, idempotent order state machine, AVX2 pre-trade risk firewall, and deterministic queue-aware historical replay engine; reduced cache-cold signal-to-wire p99 latency by X% and branch mispredictions by Y% over virtual-dispatch/heap baselines while quantifying latency-driven adverse selection on historical NASDAQ ITCH replays.

#### Required Measurable Evidence Before Using This Bullet
- Committed cache-cold and cache-hot `HdrHistogram` tables.
- `perf stat` branch-miss and icache-miss diffs.
- Clang `-ftime-trace` compile-time comparisons.
- Annotated assembly dumps and deterministic replay logs across multiple injected latency tiers.

#### High-Signal Technical Interview Questions
- Why did you measure *cache-cold* latency alongside cache-hot latency?
- How did you prevent 64-bit integer overflow when evaluating `price * qty` notional limits inside AVX2 vectors?
- Walk through the exact state transitions if an Executed fill arrives while your gateway already sent a Cancel and awaits confirmation.

#### Difficult Follow-Up Questions
- Under what microarchitectural conditions can AVX2 or AVX-512 actually *worsen* tail latency on a sporadic hot path (for example, SIMD frequency downclocking or unaligned cache-line split loads)?
- Why did Herb Sutter and Citadel Securities move away from ubiquitous template parameterization toward concrete types, and how do you decide where templates remain justified?
- How do pro-rata versus tail-of-queue cancellation assumptions bias fill-rate estimates in a historical L3 simulator?

---

### H. GitHub Presentation

Structure the repository cleanly:
- `include/ouch_sim/` (`codec/`, `risk/`, `fsm/`, `alloc/`, `sim/`)
- `src/`
- `tests/` (FSM matrix tests, differential fuzzing suite)
- `benchmarks/` (`cold_cache/`, `simd_risk/`, `pgo_lto/`)

Include a root `README.md` featuring:
- A State Transition Diagram of the order lifecycle FSM.
- Annotated Compiler Explorer (Godbolt) assembly snippets highlighting AVX2 vectorized code.
- Markout charts demonstrating how injected latency worsens execution fill quality (adverse selection).
- Clear build and test reproduction instructions.

---

## Consolidated Hardware and Cost Breakdown in INR

All three projects achieve 100% of their technical, resume, and interview value at **₹0 mandatory hardware cost**. Every core component runs on an existing Linux PC, laptop, or dual-boot system using Linux `veth` virtual Ethernet pairs, in-memory packet replay, and open-source verification tooling.

### Detailed Cost Breakdown

| Cost Category | Item / Resource | Realistic Cost (INR) | Necessity & Engineering Justification | Free Zero-Cost Alternative |
| :--- | :--- | :--- | :--- | :--- |
| **Mandatory** | Existing Linux-capable laptop/desktop (bare-metal Linux dual-boot recommended over WSL2) | **₹0** | Provides bare-metal CPU pinning, PMU hardware counters, and real HugePages. | Dual-boot Ubuntu 24.04 or Arch Linux on existing PC (**₹0**). |
| **Mandatory** | Complete open-source toolchain (GCC/Clang, CMake, Ninja, GenMC, libxdp, liburing, HdrHistogram, perf) | **₹0** | Complete modern C++ development, formal verification, and latency profiling stack. | Standard Linux package managers (`apt`, `pacman`) (**₹0**). |
| **Mandatory** | Historical Market Data (NASDAQ TotalView-ITCH 5.0 binary archives) | **₹0** | Ingests real multi-gigabyte historical exchange data containing real market bursts. | Public NASDAQ historical ITCH archives (**₹0**). |
| **Optional (Desktop Only)** | Dual-Port 2.5GbE Intel I225-V PCIe NIC (igc driver) | **₹4,799 - ₹5,000** | Lowest-cost single-desktop setup for real physical kernel-bypass AF_XDP zero-copy DMA. | Linux `veth` pair + AF_XDP copy mode (**₹0**). |
| **Optional (Desktop Only)** | Dual-Port 10GbE SFP+ Intel X520-DA2 (ixgbe) or X540-T2 (10GBASE-T RJ45) | **₹7,659 - ₹11,000** | Enables real 10GbE AF_XDP zero-copy and DPDK Poll-Mode Driver experiments on one desktop. | Linux `veth` (AF_XDP copy mode) or DPDK `net_tap` / `net_pcap` virtual PMDs (**₹0**). |
| **Do Not Spend** | Cloud VMs for latency benchmarks, paid exchange feeds, real trading capital, enterprise workstations/FPGAs | **₹0** | Shared cloud VMs add noisy-neighbor jitter and hide bare-metal PMU/PT access; paid feeds add zero engineering proof beyond public archives. | Local isolated Linux + Valgrind Cachegrind or CodSpeed in CI (**₹0**). |

---

## How the Three Projects Complement One Another

Each repository anchors a distinct pillar of low-latency C++ engineering while composing seamlessly into a **complete electronic trading pipeline** (`itch-xsk -> shmbus-mc -> ouch-risk-sim`) with zero redundant matching-engine code.

Once all three are complete, an optional integration harness can pipe normalized L3 updates from `itch-xsk` through a `shmbus-mc` HugePage shared-memory ring into `ouch-risk-sim`, allowing you to measure **chained end-to-end p99.9 latency** directly:
- **Tail Latency Compounding**: Demonstrates firsthand why multi-stage tail latencies compound worse than simply summing individual component percentiles.

### Architectural Complementarity Across Seven Dimensions

| HFT Engineering Dimension | Project 1: itch-xsk | Project 2: shmbus-mc | Project 3: ouch-risk-sim | Combined Portfolio Signal |
| :--- | :--- | :--- | :--- | :--- |
| **1. Low-Level C++ & Memory Management** | Intrusive L3 slab pool, 32-bit indices, flat open-addressing map, zero hot-path new. | HugePages mmap, mlock, trivially-copyable IPC layout, 128B alignment. | Custom slab allocator, concrete constexpr codecs vs. template bloat. | Proves zero-allocation mastery across pools, shared memory, and compile-time design. |
| **2. CPU Architecture & Performance** | LLC/dTLB miss reduction, branchless big-endian decode, dense BBO tick array + bitset. | MESI cache coherence, 64B vs. 128B false sharing, SMT isolation. | AVX2 SIMD SoA risk checks, cache-cold vs. cache-hot latency, static vs. virtual dispatch, PGO/LTO. | Demonstrates mechanical sympathy from L1i/L1d/TLB caches down to assembly. |
| **3. Concurrency & Lock-Free Programming** | Single-threaded pinned hot path (lock-free by architecture). | **Primary Anchor:** SPSC/SPMC rings, SeqLock, C++20 acquire/release, **GenMC RC11/IMM verification**. | Deterministic single-threaded FSM reconciling asynchronous execution events. | Shows both when to avoid multithreading and how to formally verify atomics when needed. |
| **4. Networking & Market Data Processing** | **Primary Anchor:** MoldUDP64, A/B arbitration, gap recovery, recvmmsg vs. io_uring vs. AF_XDP. | Cross-process shared-memory IPC bypassing kernel sockets entirely. | OUCH 5.0 variable-length binary execution framing. | Covers the full inbound-to-IPC-to-outbound trading data path. |
| **5. Financial Market Mechanics** | **Primary Anchor (Market Data):** Full NASDAQ ITCH 5.0 L3 order lifecycle and NOII. | Exchange-style deterministic sequencer and event-sourced input log. | **Primary Anchor (Execution):** OUCH 5.0, pre-trade risk, STP, FIFO queue priority, fees, and adverse selection. | Bridges core C++ infrastructure and quantitative development without fabricated alpha claims. |
| **6. Production Software Engineering** | Golden differential testing, A/B fault tolerance, sanitizer CI. | Crash-recovery event-sourcing replay, SIGKILL chaos testing. | Idempotent FSM, disconnect reconciliation, exhaustive state×event testing. | Reflects production-ownership reliability thinking. |
| **7. Measurement & Technical Reasoning** | Open-loop HdrHistogram, worst-burst windows, perf stat ablation matrix. | perf c2c HITM analysis, Intel PT (magic-trace) tail root-causing. | Clang -ftime-trace, assembly inspection, PGO/LTO and cache-cold profiling. | Establishes disciplined, falsifiable performance engineering. |

---

## Suggested 6-12 Month Execution Schedule

Depth beats repository count. A sustainable **9-month core schedule** (expandable to 12 months alongside college exams, or compressed to 6 months at 35-40 hours/week full-time) assumes:
- **18-22 hours/week** of focused systems engineering.
- **6-8 hours/week** of continuous DSA, C++, and OS interview drill.
- **Mandatory Rule**: Never suspend algorithmic preparation while building systems projects: timed online assessments remain the mandatory first hurdle at virtually every HFT firm.

### Milestone Execution Roadmap

| Timeline (9-Month Core / 6-Mo Fast Track) | Primary Engineering Focus | Key Deliverables & Exit Gate | Parallel Interview Preparation |
| :--- | :--- | :--- | :--- |
| **Months 1-3** *(Weeks 1-10 Fast Track)* | **Project 1: itch-xsk** (Milestones M1-M5) | Download public NASDAQ ITCH 5.0 archive; ship Golden Differential Test (Naive vs. Cache-Optimal L3 book), MoldUDP64 A/B gap recovery, all three Linux I/O backends (recvmmsg/io_uring/AF_XDP on veth), perf stat + HdrHistogram report, and full CI. | Daily C++20 fundamentals plus 5-7 medium/hard DSA problems/week (graphs, DP, bit manipulation, custom data structures). |
| **Months 4-6** *(Weeks 11-18 Fast Track)* | **Project 2: shmbus-mc** (Milestones M1-M5) | Ship 128B-padded SPSC/SPMC rings + UB-free SeqLock, zero-error **GenMC RC11/IMM verification** in CI, event-sourced crash-recovery sequencer, perf c2c HITM ablation study, and Intel PT (magic-trace) or ftrace tail-spike postmortem. | Systematic OS internals review (virtual memory, TLBs, syscalls, TCP/UDP/NAPI) and C++ memory-model drills. |
| **Months 7-8.5** *(Weeks 19-24 Fast Track)* | **Project 3: ouch-risk-sim** (Milestones M1-M5) | Ship concrete constexpr OUCH 5.0 codec + -ftime-trace comparison, custom slab allocator + idempotent order FSM, scalar vs. AVX2 risk firewall + assembly audit, PGO/LTO cache-cold benchmarks, and queue-aware ITCH replay simulator. | Mock C++ low-level design and debugging interviews; timed HackerRank/Codeforces OA practice. |
| **Months 9-12** *(Integration, Writing & Outreach)* | **End-to-End Pipeline, Open-Source PRs & Targeted Applications** | Wire optional end-to-end integration benchmark (itch-xsk -> shmbus-mc -> ouch-risk-sim); publish 2-3 deeply technical write-ups (e.g., catching an x86-invisible ring-buffer race with GenMC); submit clean PRs (tests, docs, or optimizations) to relevant open-source C++ tooling (HdrHistogram, liburing, GenMC, or rigtorp libraries) and pursue engineer-backed referrals. | Active off-campus applications across global HFTs, India-based prop/HFT firms, and Tier-1 C++ systems teams. |

---

## Final Assessment: Strengthening an Application from a Tier-3 College

Evaluate the hiring landscape with complete realism-especially in India:
- **Pedigree Screening**: Recruiting realities and developer reports indicate that top global HFT firms (Citadel Securities, Jane Street, Optiver, HRT, Jump Trading, and Tower Research Capital) draw heavily from top IITs and premier global universities for fresh-graduate roles.
- **Cold Application Limits**: Cold online applications from a Tier-3 college are frequently screened out before an engineer ever inspects your GitHub. No three repositories can guarantee bypassing automated resume filters or substitute for clearing timed algorithmic online assessments.

What `itch-xsk`, `shmbus-mc`, and `ouch-risk-sim` realistically accomplish is shifting your odds through **four concrete mechanisms**:

### Mechanism 1: Converting Cold Outreach into Engineer-Backed Referrals
- **Why It Works**: Recruiters screen for college names, whereas principal C++ engineers respect verifiable mechanical sympathy.
- **The Insider Referral Path**: A concise message to a low-latency C++ engineer linking directly to a **GenMC-verified lock-free ring buffer**, a **`perf c2c` HITM ablation**, or a **real NASDAQ ITCH 5.0 `AF_XDP` feed handler** gives an insider objective technical grounds to refer you past pedigree screening.

### Mechanism 2: Excelling in Deep Technical and Systems Interview Rounds
- **Firsthand Empirical Reasoning**: Once you reach rounds probing C++ memory models, low-level systems reasoning, Linux networking, concurrency, and failure-mode judgment (documented across Tower Research Capital and Citadel Securities engineering loops), you will reason from firsthand empirical debugging.
- **Deeper Than Textbook Knowledge**: Having personally fixed `perf c2c` cache-line bouncing, diagnosed `AF_XDP` ring stalls, and analyzed GenMC counterexamples sets you completely apart from candidates reciting memorized textbook summaries.

### Mechanism 3: Unlocking Stepping Stones Along the Tier-3-to-Tier-1 Trajectory
- **The Proven Two-Step Route**: Multiple Indian developer accounts highlight a realistic two-step route:
  1. Joining an India-based prop trading desk, exchange-technology vendor, brokerage OMS engineering team, or core C++ systems company (where hiring committees weight GitHub and systems depth far more flexibly than campus-restricted Tier-1 desks).
  2. Building 1-2 years of live production ownership, and then interviewing laterally at Tower, Jump, Optiver, HRT, or Citadel Securities-where demonstrated production low-latency ownership dramatically outweighs college pedigree.
- **Competitive Advantage**: This portfolio positions you far ahead of typical entry-level applicants for those stepping-stone roles.

### Mechanism 4: Asymmetric Visibility Through Technical Writing and Documented Side Doors
- **Technical Postmortems**: Publishing clear, evidence-backed engineering postmortems from these three builds reaches engineers directly.
- **Recruiting Competitions**: Participating in recruiting competitions-such as Citadel's Terminal and Datathon, which candidate reports note can bypass the standard resume pile.
- **Open-Source Contributions**: Making focused open-source contributions (explicitly noted as a positive signal by Jump Trading) provides additional pedigree-independent signals.

---

### The Final Engineering Standard

Execute these three systems with ruthless honesty, zero fabricated numbers, and steady algorithmic discipline, and your GitHub will stand as independently verifiable evidence of a systems engineer worth interviewing.
