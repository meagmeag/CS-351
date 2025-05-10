### iota.cpu
|Vector<br>Length|Wall Clock<br>Time|User Time|System Time|
|:--:|--:|--:|--:|
|10| 0.00| 0.00| 0.00|
|100| 0.00| 0.00| 0.00|
|1000| 0.00| 0.00| 0.00|
|10000| 0.00| 0.00| 0.00|
|100000| 0.00| 0.00| 0.00|
|1000000| 0.00| 0.00| 0.00|
|5000000| 0.02| 0.00| 0.02|
|100000000| 0.58| 0.09| 0.49|
|500000000| 2.96| 0.47| 2.48|
|1000000000| 5.84| 0.88| 4.96|
|5000000000|33.26| 5.84|27.41|

### iota.gpu
|Vector<br>Length|Wall Clock<br>Time|User Time|System Time| Real Time Diff | Sys Time Diff |
|:--:|--:|--:|--:| --:| --:|
|10| 0.29| 0.01| 0.27| +0.29 | +.0.27 |
|100| 0.21| 0.01| 0.19| +0.21 | +0.19|
|1000| 0.20| 0.00| 0.19| +0.20| +0.19|
|10000| 0.20| 0.01| 0.19| +0.20| +0.19|
|100000| 0.22| 0.00| 0.21| +0.22| +0.21|
|1000000| 0.20| 0.01| 0.19| +0.20| +0.19|
|5000000| 0.24| 0.01| 0.22| +0.22| +0.20|
|100000000| 0.86| 0.18| 0.67| +0.28| +0.18|
|500000000| 3.17| 0.78| 2.39| +0.21| -0.09|
|1000000000| 6.56| 1.65| 4.91| +0.72| -0.05|
|5000000000|42.94| 7.94|35.00| +9.70| +7.59|

The result is not expected because the CUDA program performed about the same as (or noticeably worse than, in the case of the largest vector) the serial C++ program. I notice that iota.gpu spent more system time than iota.cpu in most cases. This leads me to believe that the reason CUDA isn't a great solution to this problem is because is it making more syscalls related to dispatching the threads, but each thread processes one value in each chunk, so it isn't worth spending so much system time to dispatch these threads.
