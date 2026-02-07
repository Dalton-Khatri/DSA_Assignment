# Program 6: Min Heap and Max Heap Builder

## Overview
Builds a min heap and max heap from unsorted arrays using the heapify algorithm.

## Heap Representation
Heaps are stored as arrays where for element at index `i`:
- Left child: 2*i + 1  
- Right child: 2*i + 2  
- Parent: (i-1)/2

## Heap Property
- Min Heap: Parent ≤ Children  
- Max Heap: Parent ≥ Children

## Functions

1. swap(int *a, int *b) 
– Swaps two elements  
2. minHeapify(int arr[], int n, int i)
– Maintains min heap property at index i  
3. buildMinHeap(int arr[], int n) 
– Converts an array to a min heap  
4. maxHeapify(int arr[], int n, int i)
 – Maintains max heap property at index i  
5. buildMaxHeap(int arr[], int n)
 – Converts an array to a max heap  
6. printArray(int arr[], int n, const char *label) 
– Prints array elements

## Main Method
1. Define unsorted array data[]  
2. Create copies for min heap and max heap  
3. Call buildMinHeap() and buildMaxHeap()  
4. Print both heaps using printArray()

## Sample Output

![Output_6](output/output_6.png "Program 6 output")