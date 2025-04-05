# 堆疊Stack

## 1. 簡介

Stack (堆疊) 是一種遵循 **後進先出 (LIFO, Last In First Out)** 的資料結構

## 2. Stack 的基本概念

### 2.1 定義

**Stack** 是一種只允許在一端進行插入和刪除操作的資料結構，具有以下操作：
- **Push**：將元素存入堆疊頂部。
- **Pop**：從堆疊頂部移除元素。
- **Peek**：取得堆疊頂部元素但不移除。
- **Empty**：判斷堆疊是否為空。
- **Full** : 判斷堆疊是否滿。

### 2.2 Stack 的特點

- **LIFO (Last In First Out)**：最後進入的元素最先被移除。
- 操作時間複雜度：Push 和 Pop 操作皆為 $O(1)$。

## 3. Stack 的實作

### 3.1 使用陣列實作

```c
#include <stdio.h>
#include <stdlib.h>
#define MAX 1000

// Function to check if the stack is empty
int isEmpty(int top) {
    return top == -1;
}
// Function to check if the stack is full   
int isFull(int top) {
    return top == MAX - 1;
}
// Function to push an element onto the stack
void push(int stack[], int *top, int value) {
    if (isFull(*top)) {
        printf("Stack overflow\n");
        return;
    }
    stack[++(*top)] = value;
}
// Function to pop an element from the stack    
int pop(int stack[], int *top) {
    if (isEmpty(*top)) {
        printf("Stack underflow\n");
        return -1; // Return -1 to indicate an error
    }
    return stack[(*top)--];
}   
// Function to get the top element of the stack
int peek(int stack[], int top) {
    if (isEmpty(top)) {
        printf("Stack is empty\n");
        return -1; // Return -1 to indicate an error
    }
    return stack[top];
}

int main(int argc, char *argv[]) {
    int stack[MAX];
    int top = -1;
    int choice, value;
    do {
        printf("1. Push\n");
        printf("2. Pop\n");
        printf("3. Peek\n");
        printf("4. Check if empty\n");
        printf("5. Check if full\n");
        printf("6. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1:
                printf("Enter value to push: ");
                scanf("%d", &value);
                push(stack, &top, value);
                break;
            case 2:
                value = pop(stack, &top);
                if (value != -1) {
                    printf("Popped value: %d\n", value);
                }
                break;
            case 3:
                value = peek(stack, top);
                if (value != -1) {
                    printf("Top value: %d\n", value);
                }
                break;
            case 4:
                if (isEmpty(top)) {
                    printf("Stack is empty\n");
                } else {
                    printf("Stack is not empty\n");
                }
                break;
            case 5:
                if (isFull(top)) {
                    printf("Stack is full\n");
                } else {
                    printf("Stack is not full\n");
                }
                break;
            case 6:
                printf("Exiting...\n");
                break;
            default:
                printf("Invalid choice\n");
        }
    } while (choice != 6);
    printf("Final stack contents: ");
    for (int i = 0; i <= top; i++) {
        printf("%d ", stack[i]);
    }
    printf("\n");
    return 0;
}
```

### 3.2 使用鏈結串列實作

```c
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

typedef struct Node {
    int data;
    struct Node *next;
} Node;

typedef struct {
    Node *top;
} Stack;

void init(Stack *s) {
    s->top = NULL;
}

bool isEmpty(Stack *s) {
    return s->top == NULL;
}

void push(Stack *s, int value) {
    Node *newNode = (Node *)malloc(sizeof(Node));
    if (!newNode) {
        printf("Memory allocation failed\n");
        return;
    }
    newNode->data = value;
    newNode->next = s->top;
    s->top = newNode;
}

void pop(Stack *s) {
    if (isEmpty(s)) {
        printf("Stack underflow\n");
        return;
    }
    Node *temp = s->top;
    s->top = s->top->next;
    free(temp);
}

int peek(Stack *s) {
    if (isEmpty(s)) {
        printf("Stack is empty\n");
        return -1;
    }
    return s->top->data;
}

void display(Stack *s) {
    Node *current = s->top;
    while (current) {
        printf("%d ", current->data);
        current = current->next;
    }
    printf("\n");
}

int main() {
    Stack s;
    init(&s);
    push(&s, 10);
    push(&s, 20);
    display(&s);
    pop(&s);
    printf("Top element: %d\n", peek(&s));
    return 0;
}
```

## 4. Stack 的應用

### 4.1中序轉後序

將運算式從左往右掃描

- 運算子放入到**stack**  

若stack中的運算子優先權較大或是相等的則要pop運算子  
``(``可以被任何運算子壓  
當遇到``)``則要pop運算子到``(``  
使他們互相抵消。

## 5. Stack 的優缺點

### 5.1 優點

- 操作簡單，**Push** 和 **Pop** 時間複雜度為 $O(1)$。
- 可用於解決多種經典問題，如括號匹配與 **DFS**。

### 5.2 缺點

- 陣列實作的堆疊大小固定，可能浪費記憶體或發生溢出。
- 鏈結串列實作演算法較複雜。


