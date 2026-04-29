# Cache Performance Analysis — SimpleScalar SPEC2000

**Nitin Thota | MS Computer and Systems Engineering | University of Houston**  
**Course: ECE 6373 Advanced Computer Architecture | Fall 2024**

## Overview
Analyzed how cache configuration parameters affect processor performance 
using SimpleScalar sim-outorder across 10 SPEC2000 benchmarks. Simulated 
100 million instructions per benchmark after skipping 100 million 
instructions for cache warmup.

## Parameters Studied
| Parameter | Values Tested |
|---|---|
| L1 Instruction Cache Size | 8KB, 16KB, 32KB, 64KB |
| L1 Data Cache Size | 2KB, 4KB, 32KB, 128KB |
| L1 Data Cache Associativity | 1-way, 2-way, 4-way, 8-way |
| L2 Cache Size | 64KB, 128KB, 512KB, 1MB |
| Block Size (L1 & L2) | 32B, 64B, 128B, 256B |

## Benchmarks
gcc, bzip, mesa, eon, wupwise, galgel, crafty, mcf, swim, equake

## Key Results
- 30% IPC improvement on compute-heavy benchmarks (crafty, equake)
- L1 cache increase from 8KB to 64KB reduced miss rates 50-70%
- Diminishing returns at 256B block size due to over-fetching
- 4-way associativity gave best balance between miss rate and complexity

## Tools Used
- SimpleScalar sim-outorder (Linux)
- SPEC2000 benchmark suite
- Manual result analysis and graphing
