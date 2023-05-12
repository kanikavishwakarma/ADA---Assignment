//Implement a hash table data structure using linear probing collision resolution.

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define TABLE_SIZE 10

// Define the hash table structure
typedef struct HashTable {
    char* keys[TABLE_SIZE];
    int values[TABLE_SIZE];
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
    while (ht->keys[index] != NULL) {
        index = (index + 1) % TABLE_SIZE; // linear probing
    }
    ht->keys[index] = key;
    ht->values[index] = value;
}

// Search for a key in the hash table and return its value
int search(HashTable* ht, char* key) {
    unsigned int index = hash(key);
    while (ht->keys[index] != NULL) {
        if (strcmp(ht->keys[index], key) == 0) {
            return ht->values[index];
        }
        index = (index + 1) % TABLE_SIZE; // linear probing
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
