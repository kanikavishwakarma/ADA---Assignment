# Implement a randomized algorithm for the Minimum Cut Problem
import random

def min_cut(adj_list):
    while len(adj_list) > 2:
        u = random.choice(list(adj_list.keys()))
        v = random.choice(adj_list[u])
        merge(adj_list, u, v)
    return len(adj_list[u])

def merge(adj_list, u, v):
    adj_list[u].extend(adj_list[v])
    for node in adj_list[v]:
        adj_list[node].remove(v)
        adj_list[node].append(u)
    del adj_list[v]

# Analyze its expected running time and approximation ratio.
"""
To analyze the expected running time and approximation ratio of this algorithm, we can use probabilistic techniques. 
The expected running time of this algorithm is O(n^2) because each iteration involves selecting two nodes from the graph,
and there are n^2 possible pairs of nodes in the graph. However, the actual running time of the algorithm can vary depending on the structure of the graph.

The expected approximation ratio of this algorithm is 2, which means that the minimum cut found by the algorithm is at most twice the size of the true minimum cut. 
This follows from the fact that the algorithm always outputs a cut that separates the two remaining nodes in the graph, 
and the true minimum cut must also separate these nodes. Therefore, the size of the cut found by the algorithm is at most twice the size of the true minimum cut.
"""
