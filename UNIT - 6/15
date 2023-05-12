# Implement a randomized algorithm for the Subset Sum Problem

"""
Select a random subset of the given set of integers.

Compute the sum of the integers in the selected subset.

If the sum equals the target value, return the subset as the solution.

If the sum is less than the target value, 
repeat step 1 with a new random subset that includes some of the remaining integers.

If the sum is greater than the target value, 
repeat step 1 with a new random subset that excludes some of the integers in the current subset.

If no solution is found after a specified number of iterations,
 return that the problem is infeasible.
"""
import random

def subset_sum_rand(S, t):
    n = len(S)
    while True:
        T = []
        sum_T = 0
        for i in range(n):
            if random.choice([True, False]):
                T.append(S[i])
                sum_T += S[i]
        if sum_T == t:
            return T

# analyze its expected running time using probabilistic techniques
"""
To analyze the expected running time of the randomized algorithm for the Subset Sum Problem,
 we need to consider the probability that the algorithm finds a solution within a certain number of iterations.

Let's assume that the input set contains n elements, 
and the target sum is t. Also, 
let's assume that each element has a uniform probability p of being chosen at each iteration of the algorithm.

The probability that a specific element is chosen at 
least once in k iterations is 1 - (1 - p)^k. 
Therefore, the probability that a specific element is never chosen in k iterations is (1 - p)^k.

Using this, we can calculate the probability that a particular subset 
of size m does not contain any element that sums up to the target t in k iterations. 
This probability is given by (1 - (1-p)^k)^m.

Let's assume that the number of subsets of size m in the input set is C. The probability that none of these subsets contains any element that sums up to the target t in k iterations is (1 - (1-p)^k)^m^C.

Therefore, the probability that at least one subset of size m contains elements that sum up to the target t in k iterations is 1 - (1 - (1-p)^k)^m^C.

Using this, we can calculate the expected number of iterations required for the algorithm to find a solution. Let E be the expected number of iterations, and let p be the probability that a randomly chosen subset of size m contains elements that sum up to the target t. Then, the probability that the algorithm finds a solution within k iterations is 1 - (1 - p)^E.

Therefore, we can solve for E as follows:

1 - (1 - p)^E = 1 - delta

where delta is the probability of failure, i.e., the probability that the algorithm does not find a solution within a given number of iterations.

Solving for E, we get:

E = ln(1 - delta)/ln(1 - p)

This gives us an estimate of the expected number of iterations required for the algorithm to find a solution with a certain probability of success. We can use this to estimate the running time of the algorithm by multiplying E by the time required to perform each iteration.

Note that this analysis assumes that each iteration of the algorithm takes a constant amount of time. In practice, the running time of the algorithm may depend on the size and complexity of the input, as well as the specific implementation of the algorithm. Therefore, this analysis should be considered as a rough estimate of the expected running time of the algorithm.
"""
