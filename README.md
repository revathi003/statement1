# statement1
## closest pair algorithm
## step 1 :
   * Find the middle point in the sorted array, we can take P[n/2] as middle point.

## step 2 :
   * Divide the given array in two halves. The first subarray contains points from P[0] to P[n/2]. The second subarray contains points from P[n/2+1] to P[n-1].

## step 3 :
   * Recursively find the smallest distances in both subarrays. Let the distances be dl and dr. Find the minimum of dl and dr. Let the minimum be d.
![mindis](https://user-images.githubusercontent.com/69565013/90004720-c0324c80-dcb3-11ea-896c-87a6186abf8e.png)

## step 4 :
   * From the above 3 steps, we have an upper bound d of minimum distance. Now we need to consider the pairs such that one point in pair is from the left half and the other is from the right half. Consider the vertical line passing through P[n/2] and find all points whose x coordinate is closer than d to the middle vertical line. Build an array strip[] of all such points.
     ![closepair](https://user-images.githubusercontent.com/69565013/90004996-3171ff80-dcb4-11ea-9824-3a0aa12747ae.png)
## step 5 :
   * Sort the array strip[] according to y coordinates. This step is O(nLogn). It can be optimized to O(n) by recursively sorting and merging.
![closepair](https://user-images.githubusercontent.com/69565013/90004996-3171ff80-dcb4-11ea-9824-3a0aa12747ae.png)

## step 6 :
   * Find the smallest distance in strip[]. This is tricky. From the first look, it seems to be a O(n^2) step, but it is actually O(n). It can be proved geometrically that for every point in the strip, we only need to check at most 7 points after it (note that strip is sorted according to Y coordinate). See this for more analysis.
## step 7:
   * Finally return the minimum of d and distance calculated in the above step (step 6)
