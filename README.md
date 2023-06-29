# python-speedup-comparison

This is an example of a speed comparison between numpy, numba, cython, and c.

The comparison is done on the problem of calculating pair distances between two lists of points.
Two matrixes (A[n,k], C[m,k]) contain vectors of length k, and the euclidian distances of each pair should be output in a matrix R[n,m].

If you face this problem in your own work, the obvious answer is to use r4 = scipy.spatial.distance.cdist(a,b, 'euclidean').

For n, m, k = 2001, 1001, 300 on my laptop the results are:
- naive numpy 2.02 s
- naive c 1.68 s
- numba 0.90 s
- hybrid numpy 0.77 s
- cython 0.65 s
- [scipy.spatial.distance.cdist 0.27 s]


Note: this compiles and runs on my machine (ubuntu 20.04, python 3.8). 
I do not expect the c code to compile on windows without changes. (The c code could probably be greatly improved in terms of speed as well).
