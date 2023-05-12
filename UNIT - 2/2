//Implement a recursive algorithm for computing the Fibonacci sequence using divide-and-conquer.


#include <stdio.h>

int fibonacci(int n) {
    if (n == 0) {
        return 0;
    } else if (n == 1) {
        return 1;
    } else {
        // Divide the problem into two smaller subproblems
        int left = fibonacci(n - 1);
        int right = fibonacci(n - 2);
        // Conquer the subproblems by combining the results
        return left + right;
    }
}

int main() {
    int n;
    printf("Enter a positive integer: ");
    scanf("%d", &n);

    int result = fibonacci(n);
    printf("Fibonacci(%d) = %d\n", n, result);

    return 0;
}
