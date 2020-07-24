#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a) O(n^3) / O(n^2) => O(n) linear
    the while loop increases by n^3, but since the statement below increases by n^2, the exponents cancel out and the runtime is O(n) linear.


b) O(n) * O( log(n)) => O(n log(n)) linearithmic
    the for loop increases at a linear rate to input n. however the statement in the while loop increases at a logarithmic rate to input n. The runtime is O(n log(n))


c) O(n) linear
    The number of times the recursive call is being executed directly correlates to the number of bunnies passed in as input n.

## Exercise II


For this problem, I would use a binary search approach.
Starting at the middle floor, we could test to see if the egg breaks. By doing this we can immediately rule out the lower half for being less than f or the upper half for being greater than f.

low = 0
high = len(floors)
middle = (low + high) // 2

We start by testing the egg from the middle floor. If it does not break, we can eliminate every floor below the middle and try again from the new middle. 

low = middle + 1
high = high
middle = (low + high) //2

If the egg does break, we can eliminate every floor above, knowing the egg will also break from a higher floor. We do this by setting the new high value to middle - 1.

high = middle - 1
low = low
middle = (low + high) // 2

We repeat this process until we have found the value of f, the highest possible floor we can drop the egg from without breaking.

The runtime complexity for this algorithm is O(log n). It increases at a logartihmic rate, because we are ruling out a chunk of possibilities with every execution.