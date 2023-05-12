//Implement a divide-and-conquer algorithm for finding the maximum subarray sum of a given array of integers.


#include <stdio.h>
#include <limits.h>

int max(int a, int b) {
    return (a > b) ? a : b;
}

int maxCrossingSum(int arr[], int low, int mid, int high) {
    int left_sum = INT_MIN, right_sum = INT_MIN, sum = 0;
    for (int i = mid; i >= low; i--) {
        sum += arr[i];
        if (sum > left_sum) {
            left_sum = sum;
        }
    }
    sum = 0;
    for (int i = mid+1; i <= high; i++) {
        sum += arr[i];
        if (sum > right_sum) {
            right_sum = sum;
        }
    }
    return max(max(left_sum + right_sum, left_sum), right_sum);
}

int maxSubarraySum(int arr[], int low, int high) {
    if (low == high) {
        return arr[low];
    }
    int mid = (low + high) / 2;
    return max(maxSubarraySum(arr, low, mid),
            max(maxSubarraySum(arr, mid+1, high),
                maxCrossingSum(arr, low, mid, high)));
}

int main() {
    int arr[] = { -2, -5, 6, -2, -3, 1, 5, -6 };
    int n = sizeof(arr) / sizeof(arr[0]);
    int max_sum = maxSubarraySum(arr, 0, n-1);
    printf("Maximum subarray sum is %d", max_sum);
    return 0;
}
