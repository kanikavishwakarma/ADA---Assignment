# def knapsack_greedy(values, weights, capacity):
    n = len(values)
    items = list(zip(values, weights))
    items.sort(key=lambda x: x[0], reverse=True) # sort in decreasing order of values
    total_value = 0
    knapsack = []
    for v, w in items:
        if capacity >= w:
            knapsack.append((v, w))
            total_value += v
            capacity -= w
        else:
            break
    return total_value, knapsack
