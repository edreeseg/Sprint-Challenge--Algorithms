#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a)  This block of code would be O(n) runtime complexity.  We're executing a loop comparing `a` with `n^3`, but we are also added `n^2` to `a` with each loop.  This leads to a total of `n` operations being performed before the loop terminates.


b)  This block of code would be O(nlogn).  Our outer loop executes a total of `n` times, and we have a nested loop executing `logn` operations, because `j` is growing exponentially - being doubled each time.


c) This block of code would be O(n) runtime complexity where `n == bunnies`.  We're calling `bunnyEars` recursively, but the number of operations is only ever increasing in a strictly linear fashion.

## Exercise II

You can treat an n-story building as essentially being a sorted list of numbers representing the floors (e.g. [1, 2, 3, ...n]).  With this in mind, we can execute a binary search to determine the correct value of `f` by testing middle and its surrounding floor with each pass, and slowly whittling the size of the possibilities down until we know for sure `f` must be either the remaining value, or the value above it.

The runtime would be O(logn), though it may be complicated by the extra comparisons we're making on each pass.  Still, this should only represent linear growth, and the possibility of finding `f` before the list is of size `1` is worth the extra comparisons.

def floor_search(floors, left, right):
  if left == right:
    if egg breaks when dropped from floors[left]:
      return left
    else:
      return left+1
  middle = left+right//2
  egg_breaks_at_middle = boolean representing if egg breaks
  if egg_breaks_at_middle and egg does not break when dropped from middle - 1:
    return middle
  if not egg_breaks_at_middle and egg breaks when dropped from middle + 1:
    return middle + 1
  if egg_breaks_at_middle:
    return floor_search(floors, left, middle-1)
  else:
    return floor_search(floor, middle+1, right)