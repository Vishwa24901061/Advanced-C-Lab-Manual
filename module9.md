EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
```
#include <stdio.h>

#define MAX 5 
int stack[MAX];
int top = -1;
void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements are:\n");
    for (int i = top; i >= 0; i--) {
        printf("%d ", stack[i]);
    }
    printf("\n");
}
void push(int value) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %d onto the stack.\n", value);
    } else {
        stack[++top] = value;
        printf("%d pushed onto the stack.\n", value);
    }
}
int pop() {
    if (top == -1) {
        printf("Stack Underflow! No element to pop.\n");
        return -1;
    } else {
        int poppedValue = stack[top--];
        printf("%d popped from the stack.\n", poppedValue);
        return poppedValue;
    }
}
int main() {
    push(10);
    push(20);
    push(30);
    push(40);
    push(50);
    
    display();
    
    pop();
    display();
    push(60);
    display();
    
    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/ec70c05e-6441-441e-b0ff-c02e6a03741a)


Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:

```
#include <stdio.h>

#define MAX 5  
float stack[MAX];
int top = -1;
void push(float value) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %.2f onto the stack.\n", value);
    } else {
        stack[++top] = value;
        printf("%.2f pushed onto the stack.\n", value);
    }
}
int main() {
    float element;
    printf("Enter a floating-point number to push into the stack: ");
    scanf("%f", &element);
    push(element);
    printf("Current stack contents after pushing %.2f:\n", element);
    for (int i = top; i >= 0; i--) {
        printf("%.2f ", stack[i]);
    }
    printf("\n");

    return 0;
}
```
Output:



![Screenshot 2025-04-26 105148](https://github.com/user-attachments/assets/024297d0-0447-4b5b-b95e-ef545140781f)



Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
```
#include <stdio.h>

#define MAX 5  
int queue[MAX];
int front = -1, rear = -1;
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements are: ");
    for (int i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");
}

void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow! Cannot enqueue %d.\n", value);
    } else {
        if (front == -1)   
            front = 0;
        queue[++rear] = value;
        printf("%d enqueued to the queue.\n", value);
    }
}

int dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue Underflow! No elements to dequeue.\n");
        return -1;
    } else {
        int dequeuedValue = queue[front++];
        printf("%d dequeued from the queue.\n", dequeuedValue);
        return dequeuedValue;
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    
    display();
    
    dequeue();
    
    display();
    
    enqueue(40);
    enqueue(50);
    
    display();
    
    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/7b92fc4c-0cf3-436c-b467-099d964f19fe)

Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:
```
#include <stdio.h>

#define MAX 5  
float queue[MAX];
int front = -1, rear = -1;
void enqueue(float value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow! Cannot enqueue %.2f.\n", value);
    } else {
        if (front == -1) {  
            front = 0;
        }
        queue[++rear] = value;  
        printf("%.2f enqueued to the queue.\n", value);
    }
}

void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements are: ");
    for (int i = front; i <= rear; i++) {
        printf("%.2f ", queue[i]);
    }
    printf("\n");
}

int main() {
    enqueue(10.5);
    enqueue(20.3);
    enqueue(30.8);
    enqueue(40.1);
    enqueue(50.7);
    display();
    enqueue(60.4);  

    return 0;
}
```

Output:

![Screenshot 2025-04-26 105735](https://github.com/user-attachments/assets/30a4c59a-56c3-4520-9ed7-a283a4240148)


Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:
```
#include <stdio.h>

#define MAX 5  
int queue[MAX];
int front = -1, rear = -1;

void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue is empty. No elements to delete.\n");
        return;
    } else {
        printf("Element %d dequeued from the queue.\n", queue[front]);
        front++;

        if (front > rear) {
            front = rear = -1;  
            printf("Queue is now empty.\n");
        }
    }
}
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow! Cannot enqueue %d.\n", value);
    } else {
        if (front == -1) {  
            front = 0;
        }
        queue[++rear] = value;  
        printf("%d enqueued to the queue.\n", value);
    }
}

void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements are: ");
    for (int i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();

    
    dequeue();  
    display(); 

    dequeue();  
    display();
    enqueue(40);
    enqueue(50);
    display();  
    dequeue();  
    dequeue(); 
    dequeue(); 
    display(); 

    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/cd55d657-14ef-4f6d-9e2b-a827fa503e11)


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
