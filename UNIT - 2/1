//Implement a recursive algorithm for computing the factorial of a given positive integer using divide-and-conquer.


#include <stdio.h>

int factorial(int n) {
    // Base case: 0! = 1
    if (n == 0) {
        return 1;
    } else {
        // Divide the problem into a smaller subproblem
        int subfactorial = factorial(n - 1);
        // Conquer the subproblem by combining the result with the current integer
        return n * subfactorial;
    }
}

int main() {
    int n;
    printf("Enter a positive integer: ");
    scanf("%d", &n);

    int result = factorial(n);
    printf("%d! = %d\n", n, result);

    return 0;
}
