**Please read this doc from the code view.**

--PROJECT 1-----------------------------------------------------------------------------------------------------------------------------
NO OPTIMIZATION
PROGRAM     REAL TIME       USER TIME       SYS TIME        MEMORY                  THROUGHPUT                      IMPROVEMENT FROM HASH-00
hash-00:    354.26 real     341.92 user     9.96 sys        2884 memory (KB)        2,822.79 hashes per second      ---
hash-01:    17.28 real      15.69 user      1.40 sys        2880 memory (KB)        57,870.37 hashes per second     20.50
hash-02:    15.67 real      14.27 user      1.20 sys        3460 memory (KB)        63,816.21 hashes per second     22.61       
hash-03:    16.50 real      15.10 user      1.18 sys        3468 memory (KB)        60,606.06 hashes per second     21.47
hash-04:    14.45 real      13.85 user      0.41 sys        5008908 memory (KB)     69,204.15 hashes per second     24.52

O1 OPTIMIZATION
PROGRAM     REAL TIME       USER TIME       SYS TIME        MEMORY                  THROUGHPUT                      IMPROVEMENT FROM HASH-00
hash-00:    341.06 real     333.84 user     4.26 sys        2888 memory (KB)        2,932.04 hashes per second      ---
hash-01:    7.87 real       6.50 user       1.26 sys        2880 memory (KB)        127,064.80 hashes per second    43.34
hash-02:    8.09 real       6.66 user       1.28 sys        2888 memory (KB)        123,609.39 hashes per second    42.16       
hash-03:    8.55 real       6.74 user       1.28 sys        2888 memory (KB)        116,959.06 hashes per second    39.89
hash-04:    7.49 real       6.71 user       0.54 sys        5011776 memory (KB)     133,511.35 hashes per second    45.54

O2 OPTIMIZATION
PROGRAM     REAL TIME       USER TIME       SYS TIME        MEMORY                  THROUGHPUT                      IMPROVEMENT FROM HASH-00
hash-00:    338.41 real     329.27 user     5.95 sys        2880 memory (KB)        2,955.00 hashes per second       ---
hash-01:    7.93 real       6.76 user       1.07 sys        3464 memory (KB)        126,103.40 hashes per second    42.67
hash-02:    8.36 real       6.90 user       1.24 sys        2884 memory (KB)        119,617.22 hashes per second    40.48
hash-03:    8.27 real       6.80 user       1.21 sys        2904 memory (KB)        120,918.98 hashes per second    40.92
hash-04:    7.21 real       6.64 user       0.40 sys        5011776 memory (KB)     138,696.26 hashes per second    46.94

O3 OPTIMIZATION
PROGRAM     REAL TIME       USER TIME       SYS TIME        MEMORY                  THROUGHPUT                      IMPROVEMENT FROM HASH-00
hash-00:    337.82 real     330.41 user     4.65 sys        2880 memory (KB)        2,955.00 hashes per second       ---
hash-01:    8.13 real       6.87 user       1.14 sys        3476 memory (KB)        123,001.23 hashes per second    41.55
hash-02:    8.21 real       6.83 user       1.27 sys        2888 memory (KB)        121,802.68 hashes per second    41.14
hash-03:    8.12 real       6.80 user       1.21 sys        3464 memory (KB)        123,152.71 hashes per second    41.60
hash-04:    7.16 real       6.64 user       0.40 sys        5011784 memory (KB)     129,664.80 hashes per second    47.18

QUESTIONS:
1. The >> operation accounts for most of the runtime because most of the other operations in hash-00 are also in the other, faster programs.
2. There is not a large difference between hash-01 and hash-02 across all optimization levels.
   Although, it is notable that hash-02 was slightly faster everytime I ran the programs with no optimization.
3. There is not an appreciable difference between hash-03 and hash-01/hash-02.
4. hash-04's memory is larger because it maps Data.bin to its virtual memory, so more of its memory is used.
   Whereas the other programs allocate memory for only one value at a time.
5. I tried -O1 and -O3, which made a significant difference in time compared to no optimization but were otherwise comparable to -O2.
