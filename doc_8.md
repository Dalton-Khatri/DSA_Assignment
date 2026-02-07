# Program 8: Sorting Algorithms Comparison

## Overview
Generates a list of N random integers and sorts them using a user-selected sorting algorithm. Tracks the total number of comparisons and swaps (or moves for merge sort).

## Data Structures
- int arr[N]: Array to store random integers.
- Counters:
  - comparisons — total comparisons made by the algorithm.  
  - swaps — total swaps (or moves) performed during sorting.

## Functions

1. **resetCounters()** — Resets comparisons and swaps to zero.
2. **printArray(int arr[], int n)** — Prints the array elements.
3. **bubbleSort(int arr[], int n)** — Implements Bubble Sort and updates counters.
4. **selectionSort(int arr[], int n)** — Implements Selection Sort and updates counters.
5. **insertionSort(int arr[], int n)** — Implements Insertion Sort and updates counters.
6. **mergeSort(int arr[], int l, int r)** — Implements Merge Sort recursively. Uses helper function merge() and updates counters for moves and comparisons.

## Main Method

1. Reads the number of elements N from the user.
2. Generates N random integers in the range [1, 1000].
3. Displays the original array.
4. Prompts the user to select a sorting algorithm:
   - 1: Bubble Sort
   - 2: Selection Sort
   - 3: Insertion Sort
   - 4: Merge Sort
5. Sorts the array using the chosen algorithm.
6. Prints the sorted array.
7. Displays the total number of comparisons and swaps (or moves for merge sort).

## Sample Output

![Output_8a](output/output_8a.png "Program 8a output")
![Output_8b](output/output_8b.png "Program 8b output")
![Output_8c](output/output_8c.png "Program 8c output")
![Output_8d](output/output_8d.png "Program 8d output")



