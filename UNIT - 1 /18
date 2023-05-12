//Implement a hash table data structure using separate chaining collision resolution.

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define TABLE_SIZE 10

// Define a node structure for the linked list
typedef struct Node {
    char* key;
    int value;
    struct Node* next;
} Node;

// Define the hash table structure
typedef struct HashTable {
    Node* table[TABLE_SIZE];
} HashTable;

// Hash function that takes a string and returns an index into the table
unsigned int hash(char* key) {
    unsigned int hashval = 0;
    for (int i = 0; i < strlen(key); i++) {
        hashval = key[i] + (hashval << 5) - hashval;
    }
    return hashval % TABLE_SIZE;
}

// Insert a key-value pair into the hash table
void insert(HashTable* ht, char* key, int value) {
    unsigned int index = hash(key);
    Node* new_node = (Node*) malloc(sizeof(Node));
    new_node->key = key;
    new_node->value = value;
    new_node->next = NULL;
    if (ht->table[index] == NULL) {
        ht->table[index] = new_node;
    } else {
        Node* curr = ht->table[index];
        while (curr->next != NULL) {
            curr = curr->next;
        }
        curr->next = new_node;
    }
}

// Search for a key in the hash table and return its value
int search(HashTable* ht, char* key) {
    unsigned int index = hash(key);
    Node* curr = ht->table[index];
    while (curr != NULL) {
        if (strcmp(curr->key, key) == 0) {
            return curr->value;
        }
        curr = curr->next;
    }
    return -1; // not found
}

// Main function for testing the hash table
int main() {
    HashTable ht;
    memset(&ht, 0, sizeof(HashTable));
    insert(&ht, "apple", 5);
    insert(&ht, "banana", 7);
    insert(&ht, "orange", 3);
    printf("Value for 'apple': %d\n", search(&ht, "apple"));
    printf("Value for 'banana': %d\n", search(&ht, "banana"));
    printf("Value for 'orange': %d\n", search(&ht, "orange"));
    printf("Value for 'pear': %d\n", search(&ht, "pear"));
    return 0;
}
