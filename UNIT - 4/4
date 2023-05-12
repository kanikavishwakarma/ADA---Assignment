# Implement the activity selection problem using a greedy approach in Python.

def activity_selection(start, finish):
    n = len(start)
    selected = [0] * n
    selected[0] = 1
    last_selected = 0
    for i in range(1, n):
        if start[i] >= finish[last_selected]:
            selected[i] = 1
            last_selected = i
    return [i for i in range(n) if selected[i] == 1]
