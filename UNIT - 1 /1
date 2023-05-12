// Implement a binary search algorithm for an array of integers.

// Algorithm
function binary_search(arr : in Integer_Array; key : in Integer) return Integer is
    low, high, mid : Integer := 0;
begin
    high := arr'Length - 1;

    while low <= high loop
        mid := (low + high) / 2;
        if arr(mid) = key then
            return mid;
        elsif arr(mid) < key then
            low := mid + 1;
        else
            high := mid - 1;
        end if;
    end loop;

    return -1; -- key not found
end binary_search;


// code in c 
#include <stdio.h>

int binary_search(int arr[], int n, int key) {
    int low = 0;
    int high = n - 1;

    while (low <= high) {
        int mid = (low + high) / 2;
        if (arr[mid] == key) {
            return mid;
        } else if (arr[mid] < key) {
            low = mid + 1;
        } else {
            high = mid - 1;
        }
    }

    return -1; // key not found
}

int main() {
    int arr[] = {2, 4, 6, 8, 10};
    int n = sizeof(arr) / sizeof(arr[0]);
    int key = 6;

    int index = binary_search(arr, n, key);

    if (index != -1) {
        printf("Key found at index %d\n", index);
    } else {
        printf("Key not found\n");
    }

    return 0;
}
