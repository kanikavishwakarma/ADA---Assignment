//Implement a recursive algorithm for computing the Euclidean distance between two points in 2D space using divide-and-conquer.


#include <stdio.h>
#include <math.h>

double euclidean_distance(double x1, double y1, double x2, double y2) {
    if (x1 == x2 && y1 == y2) {
        // Base case: the two points are the same
        return 0.0;
    } else {
        // Divide the problem into a smaller subproblem
        double mid_x = (x1 + x2) / 2.0;
        double mid_y = (y1 + y2) / 2.0;
        double dist1 = euclidean_distance(x1, y1, mid_x, mid_y);
        double dist2 = euclidean_distance(mid_x, mid_y, x2, y2);
        // Conquer the subproblems by adding their distances
        return dist1 + dist2;
    }
}

int main() {
    double x1, y1, x2, y2;
    printf("Enter the coordinates of the first point: ");
    scanf("%lf %lf", &x1, &y1);
    printf("Enter the coordinates of the second point: ");
    scanf("%lf %lf", &x2, &y2);

    double distance = euclidean_distance(x1, y1, x2, y2);
    printf("The Euclidean distance between (%.2lf, %.2lf) and (%.2lf, %.2lf) is %.2lf\n",
           x1, y1, x2, y2, distance);

    return 0;
}
