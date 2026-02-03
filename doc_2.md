# Program 2: Infix to Postfix Conversion and Evaluation

## Overview
This program converts mathematical expressions from infix notation (e.g., `a+b`) to postfix notation (e.g., `ab+`) and evaluates the postfix expression using stacks.

## Data Structures

### CharStack Structure
```c
typedef struct {
    char data[MAX_SIZE];  // Array to store characters
    int top;              // Index of top element
} CharStack;
```
Purpose: Used during infix to postfix conversion to temporarily store operators.

### IntStack Structure
```c
typedef struct {
    int data[MAX_SIZE];  // Array to store integers
    int top;             // Index of top element
} IntStack;
```
Purpose: Used during postfix evaluation to store operands and intermediate results.

## Why Two Different Stacks?
- CharStack: Conversion requires storing operators (characters)
- IntStack: Evaluation requires storing numeric values (integers)

## Functions Implemented

### Character Stack Operations

#### 1. `void initCharStack(CharStack *s)`
- Initializes character stack with top = -1

#### 2. `bool isCharStackEmpty(CharStack *s)`
- Returns true if character stack is empty

#### 3. `void pushChar(CharStack *s, char ch)`
- Pushes a character onto the stack

#### 4. `char popChar(CharStack *s)`
- Pops and returns top character

#### 5. `char peekChar(CharStack *s)`
- Returns top character without removing it

### Integer Stack Operations

#### 6. `void initIntStack(IntStack *s)`
- Initializes integer stack with top = -1

#### 7. `bool isIntStackEmpty(IntStack *s)`
- Returns true if integer stack is empty

#### 8. `void pushInt(IntStack *s, int val)`
- Pushes an integer onto the stack

#### 9. `int popInt(IntStack *s)`
- Pops and returns top integer

### Helper Functions

#### 10. `bool isOperator(char ch)`
- Purpose: Checks if character is +, -, *, /, ^, or %
- Returns: true if operator

#### 11. `int getPrecedence(char op)`
- Purpose: Returns operator precedence level
- Precedence Levels:
  - Level 1: `+`, `-`
  - Level 2: `*`, `/`, `%`
  - Level 3: `^` (exponentiation)
- Returns: Integer representing precedence (higher = higher precedence)

#### 12. `bool isRightAssociative(char op)`
- Purpose: Checks if operator is right associative
- Note: Only `^` (power) is right associative
- Example: `2^3^2` = `2^(3^2)` = 512, not `(2^3)^2` = 64

### Core Conversion Function

#### 13. `void infixToPostfix(const char *infix, char *postfix)`
- Purpose: Converts infix expression to postfix
- Algorithm (Shunting Yard Algorithm):
  1. Scan infix expression from left to right
  2. If operand: Add to postfix output
  3. If '(': Push to stack
  4. If ')': Pop stack until '(' is found, add to postfix
  5. If operator: 
     - Pop operators with higher or equal precedence (considering associativity)
     - Push current operator
  6. At end: Pop all remaining operators to postfix

- Visual Output: Shows step-by-step conversion with stack state

### Core Evaluation Function

#### 14. `int performOperation(int operand1, int operand2, char operator)`
- Purpose: Performs arithmetic operation
- Supported Operations: +, -, *, /, %, ^
- Returns: Result of operation

#### 15. `int evaluatePostfix(const char *postfix)`
- Purpose: Evaluates postfix expression
- Algorithm:
  1. Scan postfix expression from left to right
  2. If operand: Push to stack
  3. If operator:
     - Pop two operands from stack
     - Apply operation
     - Push result back to stack
  4. Final result: Top of stack

## Main Method Organization

The `main()` function is structured as:

1. Test Cases: Demonstrates conversion and evaluation with 5 examples:
   - `3+4*2` → `342*+` → Result: 11
   - `(3+4)*2` → `34+2*` → Result: 14
   - `2^3^2` → `232^^` → Result: 512
   - `5+((1+2)*4)-3` → `512+4*+3-` → Result: 14
   - `a+b*c-d` → `abc*+d-` → (Variable expression, no evaluation)
2. Smart Evaluation: Only evaluates expressions with numeric values

## Sample Output

![Output_2](output/output_2.png "Program 2 output")
