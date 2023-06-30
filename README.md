# python-speedup-comparison

This is an example of a speed comparison between numpy, numba, cython, and c.

The comparison is done on the problem of calculating pair distances between two lists of points.
Two matrixes (A[n,k], C[m,k]) contain vectors of length k, and the euclidian distances of each pair should be output in a matrix R[n,m].

If you face this problem in your own work, the obvious answer is to use r = scipy.spatial.distance.cdist(a,b, 'euclidean').

For n, m, k = 2001, 1001, 300 on my [linux]laptop the results are:
- naive numpy 1.99 s
- numba 0.89 s
- hybrid numpy 0.76 s
- cython 0.65 s
- c_extension c 0.33 s
- minimal c 0.32 s
- [scipy.spatial.distance.cdist 0.25 s]

For n, m, k = 2001, 1001, 300 on my [old, windows]desktop the results are:
- naive numpy 4.18 s
- hybrid numpy 3.91 s
- numba 1.10 s
- cython 0.75 s
- [scipy.spatial.distance.cdist 0.69 s]
- c_extension c 0.26 s
- minimal c 0.23 s

Note: this compiles and runs on my machines (ubuntu 20.04/windows 10, python 3.8). If you lack the proper compilers python *should* tell you where you can get them.
