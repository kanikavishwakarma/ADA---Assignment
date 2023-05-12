//Implement a recursive algorithm for computing the greatest common divisor of two integers using divide-and-conquer.


#include <stdio.h>

int gcd(int a, int b) {
    if (b == 0) {
        return a;
    } else {
        // Divide the problem into a smaller subproblem
        int remainder = a % b;
        // Conquer the subproblem by recursively computing the GCD of b and the remainder
        return gcd(b, remainder);
    }
}

int main() {
    int a, b;
    printf("Enter two positive integers: ");
    scanf("%d %d", &a, &b);

    int result = gcd(a, b);
    printf("GCD(%d, %d) = %d\n", a, b, result);

    return 0;
}
