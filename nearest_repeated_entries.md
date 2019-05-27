# Find the nearest repeated entries in an array

One way of improving time complexity at the expense of space complexity is to use a cache.
This avoids redundant computations as the results to previous work can be accessed in `O(1)` time.