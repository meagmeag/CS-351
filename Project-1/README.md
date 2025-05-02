# PROJECT 1

## NO OPTIMIZATION
| PROGRAM | REAL TIME | USER TIME | SYS TIME | MEMORY | THROUGHPUT | IMPROVEMENT FROM HASH-00 |
| --- | --- | --- | --- | --- | --- | --- |
hash-00 | 354.26  | 341.92  | 9.96  | 2884 (KB) | 2,822.79 hashes/second | ---
hash-01 | 17.28  | 15.69  | 1.40  | 2880 (KB) | 57,870.37 hashes/second | 20.50
hash-02 | 15.67  | 14.27  | 1.20  | 3460 (KB) | 63,816.21 hashes/second | 22.61 
hash-03 | 16.50  | 15.10  | 1.18  | 3468 (KB) | 60,606.06 hashes/second | 21.47
hash-04 | 14.45  | 13.85  | 0.41  | 5008908 (KB) | 69,204.15 hashes/second | 24.52

## O1 OPTIMIZATION
| PROGRAM | REAL TIME | USER TIME | SYS TIME | MEMORY | THROUGHPUT | IMPROVEMENT FROM HASH-00 |
| --- | --- | --- | --- | --- | --- | --- |
hash-00 | 341.06 | 333.84 | 4.26 | 2888 (KB) | 2,932.04 hashes/second | ---
hash-01 | 7.87 | 6.50 | 1.26 | 2880 (KB) | 127,064.80 hashes/second | 43.34
hash-02 | 8.09 | 6.66 | 1.28 | 2888 (KB) | 123,609.39 hashes/second | 42.16 
hash-03 | 8.55 | 6.74 | 1.28 | 2888 (KB) | 116,959.06 hashes/second | 39.89
hash-04 | 7.49 | 6.71 | 0.54 | 5011776 (KB) | 133,511.35 hashes/second | 45.54

## O2 OPTIMIZATION
| PROGRAM | REAL TIME | USER TIME | SYS TIME | MEMORY | THROUGHPUT | IMPROVEMENT FROM HASH-00 |
| --- | --- | --- | --- | --- | --- | --- |
hash-00 | 338.41 | 329.27 | 5.95 | 2880 (KB) | 2,955.00 hashes/second | ---
hash-01 | 7.93 | 6.76 | 1.07 | 3464 (KB) | 126,103.40 hashes/second | 42.67
hash-02 | 8.36 | 6.90 | 1.24 | 2884 (KB) | 119,617.22 hashes/second | 40.48
hash-03 | 8.27 | 6.80 | 1.21 | 2904 (KB) | 120,918.98 hashes/second | 40.92
hash-04 | 7.21 | 6.64 | 0.40 | 5011776 (KB) | 138,696.26 hashes/second | 46.94

## O3 OPTIMIZATION
| PROGRAM | REAL TIME | USER TIME | SYS TIME | MEMORY | THROUGHPUT | IMPROVEMENT FROM HASH-00 |
| --- | --- | --- | --- | --- | --- | --- |
hash-00 | 337.82 | 330.41 | 4.65 | 2880 (KB) | 2,955.00 hashes/second | ---
hash-01 | 8.13 | 6.87 | 1.14 | 3476 (KB) | 123,001.23 hashes/second | 41.55
hash-02 | 8.21 | 6.83 | 1.27 | 2888 (KB) | 121,802.68 hashes/second | 41.14
hash-03 | 8.12 | 6.80 | 1.21 | 3464 (KB) | 123,152.71 hashes/second | 41.60
hash-04 | 7.16 | 6.64 | 0.40 | 5011784 (KB) | 129,664.80 hashes/second | 47.18

## QUESTIONS
1. The >> operation accounts for most of the runtime. Most of the other operations in hash-00 are also in the other, faster programs. Using >> to read in each byte requires many more function calls than the other programs.
2. There was a sight difference in hash-01 and hash-02's times. With no optimization, hash-02 was consistently ~1-2 seconds faster, indicating alloca() is faster. However, with all other levels optimization, hash-01 was faster.
3. hash-03 did not have an appreciable speed difference compared to hash-01 and hash-02. In some runs, it performed better and in others worse, but was generally in the same range as the other two. The biggest difference was with no optiimization.
4. hash-04's usage is larger because it maps all of Data.bin to its virtual memory, so more of it is used at once. Whereas the other programs allocated space for only one value or set of values at a time, using less memory at any given time while hashing.
6. I tried -O1 and -O3, which made a significant difference in time compared to no optimization but were otherwise comparable to -O2.
