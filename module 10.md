EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;  
    newNode->next = NULL; 
    return newNode;
}
int search(struct Node* head, int key) {
    struct Node* current = head;  
    while (current != NULL) {
        if (current->data == key) {
            return 1; 
        }
        current = current->next;  
    }
    return 0;  
}
void display(struct Node* head) {
    struct Node* current = head;
    if (current == NULL) {
        printf("The list is empty.\n");
        return;
    }
    
    printf("Linked list elements: ");
    while (current != NULL) {
        printf("%d ", current->data);
        current = current->next;
    }
    printf("\n");
}

int main() {
    struct Node* head = createNode(10);
    struct Node* second = createNode(20);
    struct Node* third = createNode(30);
    head->next = second;
    second->next = third;
    display(head);
    int key;
    printf("Enter the element to search: ");
    scanf("%d", &key);

    if (search(head, key)) {
        printf("Element %d found in the linked list.\n", key);
    } else {
        printf("Element %d not found in the linked list.\n", key);
    }

    return 0;
}
```

Output:

![Screenshot 2025-04-26 110740](https://github.com/user-attachments/assets/d003a871-0fcf-467f-86af-349479ad6696)



Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;          
    struct Node* next; 
};

struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;  
    newNode->next = NULL;   
    return newNode;
}

void insert(struct Node** head, int value) {
    struct Node* newNode = createNode(value);  
    if (*head == NULL) {
        *head = newNode;
    } else {
        struct Node* current = *head;
        while (current->next != NULL) {
            current = current->next;
        }
        current->next = newNode;
    }
}
void display(struct Node* head) {
    if (head == NULL) {
        printf("The list is empty.\n");
        return;
    }

    struct Node* current = head;
    printf("Linked list elements: ");
    while (current != NULL) {
        printf("%d ", current->data);
        current = current->next;
    }
    printf("\n");
}

int main() {
    struct Node* head = NULL;  
    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    insert(&head, 40);

    display(head);

    return 0;
}
```
Output:


![Screenshot 2025-04-26 111039](https://github.com/user-attachments/assets/ed80a91e-8fc4-4dc6-bc86-644c1ba84dfc)

 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;          
    struct Node* next;  
    struct Node* prev;  
};

struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node)); // Allocate memory
    newNode->data = value;    
    newNode->next = NULL;     
    newNode->prev = NULL;      initially
    return newNode;
}

void traverse(struct Node* head) {
    struct Node* temp = head;  

    if (temp == NULL) {
        printf("The list is empty.\n");
        return;
    }

    printf("Doubly Linked List traversal (Forward direction):\n");
    while (temp != NULL) {
        printf("%d ", temp->data);   node
        temp = temp->next;         
    }
    printf("\n");
}

int main() {
    struct Node* head = NULL;

    // Create and link nodes
    struct Node* first = createNode(10);
    struct Node* second = createNode(20);
    struct Node* third = createNode(30);
    head = first;
    first->next = second;
    second->next = third;
    second->prev = first;
    third->prev = second;

    traverse(head);

    return 0;
}
```

Output:

![Screenshot 2025-04-26 111346](https://github.com/user-attachments/assets/09598a8b-cad4-4679-886a-6e6e3dfd14fd)



Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;           
    struct Node* next; 
    struct Node* prev;  
};

struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node)); 
    newNode->data = value;   
    newNode->next = NULL;     
    newNode->prev = NULL;  
    return newNode;
}

void insert(struct Node** head, int value) {
    struct Node* newNode = createNode(value);  

    if (*head == NULL) {
        
        *head = newNode;
    } else {
        struct Node* temp = *head;
        while (temp->next != NULL) {
            temp = temp->next; 
        }
        temp->next = newNode;     
        newNode->prev = temp;    
    }
}
void display(struct Node* head) {
    if (head == NULL) {
        printf("The list is empty.\n");
        return;
    }

    struct Node* temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d ", temp->data); 
        temp = temp->next;        
    }
    printf("\n");
}

int main() {
    struct Node* head = NULL; 
    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    insert(&head, 40);
    display(head);

    return 0;
}
```


Output:

![Screenshot 2025-04-26 111639](https://github.com/user-attachments/assets/441c007c-ec8c-44db-be11-8956ca277ed8)



Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;           
    struct Node* next; 
};

struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));  
    newNode->data = value;   
    newNode->next = NULL;   
    return newNode;
}
void deleteElement(struct Node** head, int value) {
    if (*head == NULL) {
        // Check if the linked list is empty
        printf("The list is empty. No element to delete.\n");
        return;
    }

    struct Node* temp = *head;
    struct Node* prev = NULL;

    if (temp != NULL && temp->data == value) {
        *head = temp->next; 
        free(temp);       
        printf("Element %d deleted from the list.\n", value);
        return;
    }
    while (temp != NULL && temp->data != value) {
        prev = temp;          
        temp = temp->next;     
    }
    if (temp == NULL) {
        printf("Element %d not found in the list.\n", value);
        return;
    }
    prev->next = temp->next;  
    free(temp);               
    printf("Element %d deleted from the list.\n", value);
}

void display(struct Node* head) {
    if (head == NULL) {
        printf("The list is empty.\n");
        return;
    }

    struct Node* temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%d ", temp->data);  
        temp = temp->next;         
    }
    printf("\n");
}

int main() {
    struct Node* head = NULL;  
    struct Node* first = createNode(10);
    struct Node* second = createNode(20);
    struct Node* third = createNode(30);
    struct Node* fourth = createNode(40);

    head = first;
    first->next = second;
    second->next = third;
    third->next = fourth;
    display(head);
    deleteElement(&head, 20);  
    display(head);
    deleteElement(&head, 50);  

    return 0;
}
```

Output:

![Screenshot 2025-04-26 111935](https://github.com/user-attachments/assets/cbe7a655-2cb6-437e-aa74-0bd988750dca)






Result:
Thus, the function that deletes a given element from a linked list is verified successfully.

