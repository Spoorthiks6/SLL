#include <stdio.h>
#include <stdlib.h>

// Node structure
struct Node {
    int data;
    struct Node* next;
};

struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}
  
  
  // inserting data at the beginning
void insertAtBeginning(struct Node** first, int data) {
    struct Node* newNode = createNode(data); 
    newNode->next = *first;
    *first = newNode;
}


// here we insert data at particular position mentioned
void insert(struct Node** first, int data, int pos) {
    if (pos <= 1) {
      insertAtBeginning(first, data);
    }

    struct Node* newNode = createNode(data);
    struct Node* temp = *first;
    int count = 1;

    while (temp != NULL && count < pos - 1) {
        temp = temp->next;
        count++;
    }

    if (temp == NULL) {
        printf("Position out of bounds, inserting at the end.\n");
    }

    newNode->next = temp->next;
    temp->next = newNode;
}

void display(struct Node* first) {
    struct Node* temp = first;
    while (temp) {
        printf("%d  ", temp->data);
        temp = temp->next;
    }
}

int main() {
    struct Node* first = NULL;
    
    insertAtBeginning(&first, 10);
    insertAtBeginning(&first, 20);
    insertAtBeginning(&first, 30);
    printf("After inserting at beginning: ");
    display(first);
    
    insert(&first, 25, 2);
    printf("\n After inserting 25 at position 2: ");
    display(first);
    
    insert(&first, 5, 5);
    printf("\n After inserting 5 at position 5: ");
    display(first );
    
    return 0;
}
