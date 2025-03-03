# 串列 (Linked List)

---

## 1. 串列的定義

串列是一種**動態資料結構**
需要利用**動態記憶體配置**為資料配置空間
在結構體需要宣告

- 存資料的變數
- 指向結構體的指標

## 2. 串列的特性

- **優點**
  - **節省空間**不會造成不必要的浪費
  - **插入與刪除效率高** 在已知位置時，插入與刪除操作的時間複雜度為 O(1)

- **缺點**  
  - **循序尋訪**找資料不方便，無法像陣列一樣透過索引快速存取
  - **必須對指標應用熟悉** 使用動態記憶體配置應注意**懸浮參考 或是 懸浮指標**([Dangling references or Dangling pointer](https://zh.wikipedia.org/zh-tw/%E8%BF%B7%E9%80%94%E6%8C%87%E9%92%88))
  - **額外的記憶體開銷** 每個節點都需要額外儲存指標，增加記憶體消耗

## 3. 單向串列的使用方式 (C 語言範例)

以下是**單向串列**(Single Linked List)使用

![ ](https://raw.githubusercontent.com/tim941008/note/main/resource/Singlelist.png)

### 3.1 宣告與初始化

```c
struct List{
    int value; // 資料
    struct List* next; // 指向下一個結構的指標
};
```

### 3.2 建立新節點

```c

struct List* createNode(int data) {
    struct List* newNode = (struct List*)malloc(sizeof(struct List));//分配記憶體
    if (newNode == NULL) {
        printf("記憶體分配失敗\n");
        return NULL;
    }
    newNode->value = data;
    newNode->next = NULL;
    return newNode;
}
```

### 3.3 插入節點

將節點插入至串列的開頭
![ ](https://raw.githubusercontent.com/tim941008/note/main/resource/newnode.gif)

```c
void insertAtHead(struct List** head, int data) {
    struct List* newNode = createNode(data);
    if (newNode == NULL) return;
    newNode->next = *head; //使新節點的指標指向舊頭節點
    *head = newNode;
}
```

將節點插入至串列的某個值後

![ ](https://raw.githubusercontent.com/tim941008/note/main/resource/SLLinsert.gif)

```c
void insertAfterValue(struct List** head, int target, int data) {
    struct List* temp = *head;
    while (temp != NULL && temp->value != target) {
        temp = temp->next;
    }
    if (temp == NULL) {
        printf("未找到值 %d，無法插入 %d\n", target, data);
        return;
    }
    struct List* newNode = createNode(data);
    if (newNode == NULL) return;
    newNode->next = temp->next;
    temp->next = newNode;
}
```

將值插入到串列最後

```c
void insertAtTail(struct List** head, int data) {
    struct List* newNode = createNode(data);
    if (newNode == NULL) return;
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    struct List* temp = *head;
    while (temp->next != NULL) {//找到尾節點
        temp = temp->next;
    }
    temp->next = newNode;
}
```

### 3.4 刪除節點

從串列中刪除指定值的節點

```c
void deleteNode(struct List** head, int key) {
    struct List* temp = *head, *prev = NULL;
    while (temp != NULL && temp->value != key) {
        prev = temp;
        temp = temp->next;
    }
    if (temp == NULL) return;
    if (prev == NULL) //如果目標在頭節點
        *head = temp->next;
    else
        prev->next = temp->next;
    free(temp);
}

```

### 3.5 遍歷串列

```c
void printList(struct List* head) {
    struct List* current = head;
    while (current != NULL) {
        printf("%d -> ", current->value);
        current = current->next;
    }
    puts("NULL");
}
```

228好累休息一下之後再補圖...還有reverse
😑至於動態記憶體配置在考慮出一篇C\C++語法...  
