# Program 1: Balanced Parentheses Checker

## Overview
This program checks whether a mathematical expression has balanced parentheses, brackets, and braces using a stack data structure.

## Data Structures

### Stack Structure
```c
typedef struct {
    char data[MAX_SIZE];  // Array to store characters
    int top;              // Index of top element (-1 when empty)
} Stack;
```
Purpose: The stack is used to keep track of opening brackets. When we encounter a closing bracket, we can check if it matches the most recent opening bracket by popping from the stack.

## Functions Implemented

### 1. `void initStack(Stack *s)`
- Purpose: Initializes the stack by setting top to -1
- Parameters: Pointer to Stack structure
- Returns: Nothing (void)

### 2. `bool isEmpty(Stack *s)`
- Purpose: Checks if the stack is empty
- Returns: true if stack is empty, false otherwise

### 3. `bool isFull(Stack *s)`
- Purpose: Checks if the stack has reached maximum capacity
- Returns: true if stack is full, false otherwise

### 4. `void push(Stack *s, char ch)`
- Purpose: Adds a character to the top of the stack
- Parameters: Stack pointer and character to push
- Note: Includes overflow checking

### 5. `char pop(Stack *s)`
- Purpose: Removes and returns the top character from the stack
- **Returns**: The popped character, or '\0' if stack is empty

### 6. `char peek(Stack *s)`
- Purpose: Returns the top character without removing it
- Returns: Top character or '\0' if empty

### 7. `bool isOpeningBracket(char ch)`
- Purpose: Checks if a character is '(', '[', or '{'
- Returns: true if character is an opening bracket

### 8. `bool isClosingBracket(char ch)`
- Purpose: Checks if a character is ')', ']', or '}'
- Returns: true if character is a closing bracket

### 9. `bool isMatchingPair(char opening, char closing)`
- Purpose: Verifies if two brackets form a valid pair
- Examples: '(' matches ')', '[' matches ']', '{' matches '}'
- Returns: true if brackets match

### 10. `bool areParenthesesBalanced(const char *expression)`
- Purpose: Main algorithm to check if expression has balanced parentheses
- Algorithm:
  1. Initialize an empty stack
  2. Scan the expression character by character
  3. If opening bracket: push onto stack
  4. If closing bracket: 
     - Check if stack is empty (unbalanced)
     - Pop from stack and verify it matches
  5. After scanning, stack should be empty (all brackets closed)
- Returns: true if balanced, false otherwise

### 11. `void checkAndDisplay(const char *expression)`
- Purpose: User-friendly wrapper that displays the result
- Output: Shows expression and whether it's balanced or not

## Main Method Organization

The `main()` function is structured as follows:

1. Header Display: Shows a nice title for the program
2. Predefined Test Cases: Tests the three expressions from the assignment:
   - `a + (b - c) * (d` → Unbalanced
   - `m + [a - b * (c + d * {m)]` → Unbalanced
   - `a + (b - c)` → Balanced
5. Clean Exit: Returns 0 on successful completion

## Sample Output

![Output_1](output/output_1.png "Program 1 output")

