import heapq

def dijkstra(graph, start, end):
    """
    Implementation of Dijkstra's algorithm to find the shortest path between two vertices in a graph.
    
    Args:
    - graph: a dictionary representing the graph, where the keys are the vertices and the values are lists of tuples
      representing the neighboring vertices and the weights of the edges connecting them.
    - start: the starting vertex
    - end: the ending vertex
    
    Returns:
    - A tuple containing the distance of the shortest path and the path itself as a list of vertices.
    """
    # Initialize distances and visited set
    distances = {vertex: float('inf') for vertex in graph}
    distances[start] = 0
    visited = set()
    
    # Initialize priority queue with the starting vertex and its distance
    pq = [(0, start)]
    
    while pq:
        # Get the vertex with the smallest distance
        current_distance, current_vertex = heapq.heappop(pq)
        
        # If we've already visited this vertex, continue to the next iteration
        if current_vertex in visited:
            continue
        
        # Mark the current vertex as visited
        visited.add(current_vertex)
        
        # If we've reached the end vertex, return the shortest distance and path
        if current_vertex == end:
            path = []
            while current_vertex != start:
                path.append(current_vertex)
                current_vertex = previous_vertices[current_vertex]
            path.append(start)
            path.reverse()
            return (current_distance, path)
        
        # Update distances to neighboring vertices
        for neighbor, weight in graph[current_vertex]:
            distance = current_distance + weight
            if distance < distances[neighbor]:
                distances[neighbor] = distance
                previous_vertices[neighbor] = current_vertex
                heapq.heappush(pq, (distance, neighbor))
    
    # If we haven't reached the end vertex, there is no path
    return None
