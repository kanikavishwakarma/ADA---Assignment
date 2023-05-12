//Implement a divide-and-conquer algorithm for finding the closest pair of points in 2D space.


import math

def distance(p1, p2):
    """Calculate the Euclidean distance between two points."""
    return math.sqrt((p1[0]-p2[0])**2 + (p1[1]-p2[1])**2)

def closest_pair(points):
    """Find the closest pair of points in 2D space."""
    
    def closest_pair_helper(points_x, points_y):
        """Helper function to recursively find the closest pair of points."""
        n = len(points_x)
        
        if n <= 3:
            # Find the closest pair of points using brute force.
            min_distance = float('inf')
            for i in range(n-1):
                for j in range(i+1, n):
                    dist = distance(points_x[i], points_x[j])
                    if dist < min_distance:
                        min_distance = dist
                        closest_pair = (points_x[i], points_x[j])
            return min_distance, closest_pair
        
        # Divide the points into two halves.
        mid = n // 2
        points_x_left = points_x[:mid]
        points_x_right = points_x[mid:]
        mid_x = points_x[mid][0]
        points_y_left = []
        points_y_right = []
        for point in points_y:
            if point in points_x_left:
                points_y_left.append(point)
            else:
                points_y_right.append(point)
        
        # Recursively find the closest pair of points in the left and right halves.
        min_distance_left, closest_pair_left = closest_pair_helper(points_x_left, points_y_left)
        min_distance_right, closest_pair_right = closest_pair_helper(points_x_right, points_y_right)
        min_distance = min(min_distance_left, min_distance_right)
        if min_distance == 0:
            return min_distance, (closest_pair_left or closest_pair_right)
        
        # Find the closest pair of points in the strip of width 2*min_distance.
        strip_points = []
        for point in points_y:
            if abs(point[0] - mid_x) < min_distance:
                strip_points.append(point)
        strip_points.sort(key=lambda point: point[1])
        for i in range(len(strip_points)-1):
            for j in range(i+1, min(i+8, len(strip_points))):
                dist = distance(strip_points[i], strip_points[j])
                if dist < min_distance:
                    min_distance = dist
                    closest_pair = (strip_points[i], strip_points[j])
        
        return min_distance, closest_pair
    
    # Sort the points based on their x-coordinates.
    points_x = sorted(points, key=lambda point: point[0])
    points_y = sorted(points, key=lambda point: point[1])
    
    # Recursively find the closest pair of points.
    min_distance, closest_pair = closest_pair_helper(points_x, points_y)
    
    return closest_pair
