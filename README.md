# python-speedup-comparison

This is an example of a speed comparison between numpy, numba, cython, and c.

The comparison is done on the problem of calculating pair distances between two lists of points.
Two matrixes (A[n,k], C[m,k]) contain vectors of length k, and the euclidian distances of each pair should be output in a matrix R[n,m].

If you face this problem in your own work, the obvious answer is to use r4 = scipy.spatial.distance.cdist(a,b, 'euclidean').

For n, m, k = 2001, 1001, 300 on my (somewhat old) machine the results are:
naive numpy 2.02 s
hybrid numpy 0.77 s
numba 0.90 s
cython 0.65 s
naive c 1.68 s
[scipy.spatial.distance.cdist 0.27 s]
