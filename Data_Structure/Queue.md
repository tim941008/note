# 佇列（Queue）

![image](https://hackmd.io/_uploads/By8g_7RpJx.png)

## 一、定義

佇列（Queue）是一種 **先進先出（FIFO, First-In First-Out）** 的資料結構。

- 想像成排隊買票，先排的人先被服務。
- 常見於工作排程、緩衝區、印表機任務等應用。

---

## 二、基本操作

| 操作名稱 | 說明 |
|----------|------|
| `enqueue`   | 將元素加入佇列尾端 |  
| `dequeue`   | 移除佇列前端的元素 |  
| `front`     | 查看佇列前端的元素但不移除 |  
|  `rear`     | 佇列最尾端元素|
| `isEmpty`   | 檢查佇列是否為空 |

---

## 四、C 語言實作（使用陣列）

```c
#include <stdio.h>
#define MAX 100

int queue[MAX];
int front = 0;
int rear = -1;

void enqueue(int value) {
    if (rear >= MAX - 1) {
        printf("佇列已滿\n");
        return;
    }
    queue[++rear] = value;
}

int dequeue() {
    if (front > rear) {
        printf("佇列為空\n");
        return -1;
    }
    return queue[front++];
}

int peek() {
    if (front > rear) {
        printf("佇列為空\n");
        return -1;
    }
    return queue[front];
}

int isEmpty() {
    return front > rear;
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    printf("Front 元素: %d\n", peek());
    printf("Dequeue 元素: %d\n", dequeue());
    printf("Front 元素: %d\n", peek());
    return 0;
}
```

---

## 五、應用實例

1. **工作排程（如列印佇列）**
2. **資源共享排隊（CPU、I/O 排程）**
3. **緩衝區（Buffer）實作**
4. **BFS（廣度優先搜尋）**
5. **網路封包處理**
