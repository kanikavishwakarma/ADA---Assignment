# Implement a local search algorithm for the Graph Coloring Problem, and compare its performance to that of a randomized algorithm on a set of randomly generated graphs
import random
import time

def generate_random_graph(n, p):
    graph = [[0 for i in range(n)] for j in range(n)]
    for i in range(n):
        for j in range(i+1, n):
            if random.random() < p:
                graph[i][j] = 1
                graph[j][i] = 1
    return graph

def randomized_algorithm(graph, k):
    nodes = list(range(len(graph)))
    colors = [random.randint(1, k) for i in range(len(graph))]
    for node in nodes:
        neighbors = [i for i in range(len(graph[node])) if graph[node][i] == 1]
        neighbor_colors = [colors[i] for i in neighbors]
        if colors[node] in neighbor_colors:
            colors[node] = random.randint(1, k)
    return colors

def local_search_algorithm(graph, k):
    nodes = list(range(len(graph)))
    colors = randomized_algorithm(graph, k)
    while True:
        improved = False
        for node in nodes:
            current_color = colors[node]
            for color in range(1, k+1):
                if color != current_color:
                    colors[node] = color
                    conflicts = 0
                    for i in range(len(graph)):
                        if graph[node][i] and colors[node] == colors[i]:
                            conflicts += 1
                    if conflicts == 0:
                        improved = True
                        break
            if improved:
                break
            else:
                colors[node] = current_color
        if not improved:
            break
    return colors

# Generate 10 random graphs with 50 nodes and edge probability of 0.5
graphs = [generate_random_graph(50, 0.5) for i in range(10)]

# Compare randomized algorithm and local search algorithm on each graph
for i, graph in enumerate(graphs):
    print(f"Graph {i+1}")
    print("Randomized algorithm")
    start_time = time.time()
    randomized_colors = randomized_algorithm(graph, 5)
    end_time = time.time()
    print(f"Colors: {randomized_colors}")
    print(f"Running time: {end_time - start_time:.4f} seconds")
    print("Local search algorithm")
    start_time = time.time()
    local_colors = local_search_algorithm(graph, 5)
    end_time = time.time()
    print(f"Colors: {local_colors}")
    print(f"Running time: {end_time - start_time:.4f} seconds")
