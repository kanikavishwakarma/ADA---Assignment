//Implement a divide-and-conquer algorithm for finding the kth largest element in an unsorted array of integers.


#include <stdio.h>

// Function to swap two elements in an array
void swap(int *x, int *y) {
    int temp = *x;
    *x = *y;
    *y = temp;
}

// Function to partition an array around a pivot element
int partition(int arr[], int low, int high) {
    int pivot = arr[high];
    int i = low - 1;
    
    for (int j = low; j < high; j++) {
        if (arr[j] >= pivot) {
            i++;
            swap(&arr[i], &arr[j]);
        }
    }
    
    swap(&arr[i+1], &arr[high]);
    return i+1;
}

// Function to find the kth largest element in an unsorted array
int findKthLargest(int arr[], int low, int high, int k) {
    if (k > 0 && k <= high - low + 1) {
        int pivotIndex = partition(arr, low, high);
        
        if (pivotIndex - low == k - 1) {
            return arr[pivotIndex];
        }
        
        if (pivotIndex - low > k - 1) {
            return findKthLargest(arr, low, pivotIndex-1, k);
        }
        
        return findKthLargest(arr, pivotIndex+1, high, k-(pivotIndex-low+1));
    }
    
    return -1; // k is out of range
}

// Driver code
int main() {
    int arr[] = {7, 10, 4, 3, 20, 15};
    int n = sizeof(arr) / sizeof(arr[0]);
    int k = 3; // find the 3rd largest element
    
    int kthLargest = findKthLargest(arr, 0, n-1, k);
    
    if (kthLargest != -1) {
        printf("The %dth largest element is %d", k, kthLargest);
    } else {
        printf("Invalid value of k");
    }
    
    return 0;
}
