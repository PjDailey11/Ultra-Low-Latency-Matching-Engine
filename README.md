# Ultra-Low-Latency Matching Engine

C++23 order matching engine achieving sub-280ns P99 latency via zero-allocation design and kernel-bypass I/O

## Architecture

- Price-indexed flat array order book
- Pre-allocated ring buffer memory pools (zero heap allocation on hot path)
- io_uring for kernel-bypass network I/O
- SBE message parsing for market data ingestion

## Performance Target

P99 order execution latency: <280ns (verified via rdtsc)

## Building

mkdir -p build && cd build
cmake ..
cmake --build .
