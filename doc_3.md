# Program 3: Reverse Traversal of Linked List

## Overview
This program implements and demonstrates multiple algorithms for traversing a singly linked list in reverse order without permanently modifying the list structure.

## Data Structures

### Node Structure
```c
struct Node 
{
    int data;
    struct Node* next;
};
```
## Functions Implemented

### Basic Linked List Operations

#### 1. `void reverseTraversal(struct Node* head)`
- **Purpose**: Traverses the list in reverse using recursion
- **Algorithm**:
  1. Base case: If node is NULL, return
  2. Recursively call for next node
  3. Print current node's data (on return from recursion)

## Main Method Organization

The main() function is structured as:

- Node Creation: Allocates memory for three nodes (head, second, third) and initializes their data and next pointers to form the linked list.
- List Linking: Connects nodes to create the sequence: 10 → 20 → 30 → NULL.
- Reverse Traversal: Calls reverseTraversal(head) to print the list elements in reverse order.
- Program Termination: Ends execution after displaying the reversed list.

## Sample Output

![Output_3](output/output_3.png "Program 3 output")