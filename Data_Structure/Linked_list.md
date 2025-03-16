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

### 3.6 反轉串列  

這裡使用``pre``紀錄前一節點  
``cur``代表當前節點並將此節節點反轉  
``next``為下一節點  

```c
void reverse(struct List** head) {
    struct List* prev = NULL;
    struct List* current = *head;
    struct List* next = NULL;
    while (current != NULL) {
        next = current->next;//更新至下一個節點
        current->next = prev;//反轉
        prev = current;//移動指標
        current = next;
    }
    *head = prev;
}

```

### 3.7環狀單向串列

在**環狀單向串列（Circular Singly Linked List, CSLL**中，所有節點依照單向連結的方式組成一個環，即最後一個節點的指標``next``指向第一個節點，而非 ``NULL``。

就像歌單循環播放

以下是實作

```c
#include <stdio.h>
#include <stdlib.h>
#include <windows.h>
#include <mmsystem.h>
// 環狀串列節點
typedef struct SoundNode {
    char soundFile[100];  // 存放音效檔案名稱
    struct SoundNode* next; // 指向下一個節點
} SoundNode;
// 環狀串列  
typedef struct {
    SoundNode* head; // 指向環狀串列的頭節點
} SoundList;
// 創建新節點  
SoundNode* createNode(const char* filename) {
    SoundNode* newNode = (SoundNode*)malloc(sizeof(SoundNode));
    if (newNode == NULL) {
        printf("記憶體分配失敗\n");
        return NULL;
    }
    strcpy(newNode->soundFile, filename);
    newNode->next = newNode; // 初始時自己指向自己
    return newNode;
}
// 插入音效到串列
void insertSound(SoundList* list, const char* filename) {
    SoundNode* newNode = createNode(filename);
    if (newNode == NULL) return;

    if (list->head == NULL) {
        list->head = newNode;
    } else {
        SoundNode* temp = list->head;
        while (temp->next != list->head) { // 找到最後一個節點
            temp = temp->next;
        }
        temp->next = newNode;
        newNode->next = list->head;
    }
}
// 播放當前節點的音效
void playCurrentSound(SoundNode* node) {
    if (node == NULL) return;
    printf("播放音效: %s\n", node->soundFile);
    PlaySound(TEXT(node->soundFile), NULL, SND_FILENAME | SND_SYNC); // 同步播放
}

// 循環播放所有音效
void playAllSounds(SoundList* list, int loopCount) {
    if (list->head == NULL) {
        printf("音效清單為空\n");
        return;
    }

    SoundNode* current = list->head;
    for (int i = 0; i < loopCount; i++) { // 控制循環次數
        do {
            playCurrentSound(current);
            current = current->next;
        } while (current != list->head);
    }
}

// 刪除指定音效
void deleteSound(SoundList* list, const char* filename) {
    if (list->head == NULL) return;
    SoundNode *temp = list->head, *prev = NULL;
    // 如果刪除的是頭節點
    if (strcmp(temp->soundFile, filename) == 0) {
        SoundNode* tail = list->head;
        while (tail->next != list->head) {
            tail = tail->next;
        }
        if (list->head == list->head->next) { // 只剩一個節點
            free(list->head);
            list->head = NULL;
        } else {
            list->head = temp->next;
            tail->next = list->head;
            free(temp);
        }
        return;
    }
    // 找到要刪除的節點
    do {
        prev = temp;
        temp = temp->next;
        if (strcmp(temp->soundFile, filename) == 0) {
            prev->next = temp->next;
            free(temp);
            return;
        }
    } while (temp != list->head);

    printf("未找到音效 %s\n", filename);
}

// 顯示所有音效
void printSounds(SoundList* list) {
    if (list->head == NULL) {
        printf("音效清單為空\n");
        return;
    }

    SoundNode* temp = list->head;
    do {
        printf("%s -> ", temp->soundFile);
        temp = temp->next;
    } while (temp != list->head);
    printf("(回到 %s)\n", list->head->soundFile);
}

// 測試主程式
int main() {
    SoundList soundList = { NULL };
    insertSound(&soundList, "sound1.wav");
    insertSound(&soundList, "sound2.wav");
    insertSound(&soundList, "sound3.wav");
    printSounds(&soundList);
    puts("\n開始播放循環音效");
    playAllSounds(&soundList, 2); // 播放兩輪 
    printf("\n刪除 sound2.wav\n");
    deleteSound(&soundList, "sound2.wav");
    printSounds(&soundList);

    return 0;
}

```

![ ](https://raw.githubusercontent.com/tim941008/note/main/resource/playsound.png)

---
