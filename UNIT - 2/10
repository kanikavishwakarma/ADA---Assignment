//Implement a divide-and-conquer algorithm for sorting a linked list.


#include <stdio.h>
#include <stdlib.h>

// Linked list node structure
struct Node {
    int data;
    struct Node* next;
};

// Function to merge two sorted linked lists into a single sorted list
struct Node* merge(struct Node* left, struct Node* right) {
    struct Node* result = NULL;

    // Base cases
    if (left == NULL) {
        return right;
    }
    else if (right == NULL) {
        return left;
    }

    // Recursively merge the smaller values
    if (left->data <= right->data) {
        result = left;
        result->next = merge(left->next, right);
    }
    else {
        result = right;
        result->next = merge(left, right->next);
    }

    return result;
}

// Function to split the linked list into two halves
void split(struct Node* head, struct Node** left, struct Node** right) {
    struct Node* fast;
    struct Node* slow;
    slow = head;
    fast = head->next;

    // Move the fast pointer two nodes ahead and the slow pointer one node ahead
    while (fast != NULL) {
        fast = fast->next;
        if (fast != NULL) {
            slow = slow->next;
            fast = fast->next;
        }
    }

    // The slow pointer is at the middle of the linked list
    *left = head;
    *right = slow->next;
    slow->next = NULL;
}

// Merge sort function for linked list
void mergeSort(struct Node** headRef) {
    struct Node* head = *headRef;
    struct Node* left;
    struct Node* right;

    // Base case: empty or single node linked list
    if ((head == NULL) || (head->next == NULL)) {
        return;
    }

    // Split the linked list into two halves
    split(head, &left, &right);

    // Recursively sort the left and right halves
    mergeSort(&left);
    mergeSort(&right);

    // Merge the sorted halves
    *headRef = merge(left, right);
}

// Function to print the linked list
void printList(struct Node* node) {
    while (node != NULL) {
        printf("%d ", node->data);
        node = node->next;
    }
    printf("\n");
}

// Driver program to test the merge sort algorithm
int main() {
    struct Node* head = NULL;
    struct Node* second = NULL;
    struct Node* third = NULL;

    // Create a sample linked list
    head = (struct Node*)malloc(sizeof(struct Node));
    second = (struct Node*)malloc(sizeof(struct Node));
    third = (struct Node*)malloc(sizeof(struct Node));

    head->data = 5;
    head->next = second;

    second->data = 1;
    second->next = third;

    third->data = 3;
    third->next = NULL;

    // Print the original linked list
    printf("Original linked list:\n");
    printList(head);

    // Sort the linked list using merge sort
    mergeSort(&head);

    // Print the sorted linked list
    printf("Sorted linked list:\n");
    printList(head);

    return 
