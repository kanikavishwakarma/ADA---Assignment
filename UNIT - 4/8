# Implement Prim's algorithm to find the minimum spanning tree of a given graph in flowchart.

def prim_mst(graph):
    # Initialize variables
    visited = set()
    mst = set()
    start_node = list(graph.keys())[0]
    visited.add(start_node)

    while len(visited) < len(graph):
        min_edge = None
        for node in visited:
            for neighbor, weight in graph[node].items():
                if neighbor not in visited:
                    if min_edge is None or weight < min_edge[2]:
                        min_edge = (node, neighbor, weight)
        mst.add(min_edge)
        visited.add(min_edge[1])

    return mst
