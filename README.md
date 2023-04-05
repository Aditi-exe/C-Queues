# Queues in C

In C programming language, a queue is a data structure that follows the "first-in, first-out" (FIFO) principle. It works like a real-life queue, where the first person to join the queue is the first to be served, and the last person to join the queue is the last to be served.

A queue can be represented as:

![Representation of a Queue](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20221213113312/Queue-Data-Structures.png)

Operations supported by queues include the following:

- Enqueue: Adding an element to the back of the queue. This operation is also called "push" in some programming languages.

- Dequeue: Removing an element from the front of the queue. This operation is also called "pop" in some programming languages.

- Peek: Viewing the element at the front of the queue without removing it. This operation is useful for checking the next element to be dequeued.

- IsEmpty: Checking if the queue is empty or not. This operation returns a Boolean value indicating whether or not the queue is empty.

- IsFull: Checking if the queue is full or not. This operation is usually only applicable for fixed-size queues and returns a Boolean value indicating whether or not the queue is full.

- Size: Returning the current size of the queue.

In code, queues can be implemented as follows:

```
#include <stdio.h>
#include <stdlib.h>

#define MAX_SIZE 10

int queue[MAX_SIZE];
int front = -1;
int rear = -1;

void enqueue(int value) {
    if (rear == MAX_SIZE - 1) {
        printf("Queue is full\n");
        return;
    }
    if (front == -1) {
        front = 0;
    }
    rear++;
    queue[rear] = value;
}

void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue is empty\n");
        return;
    }
    printf("Dequeued element: %d\n", queue[front]);
    front++;
}

void display() {
    if (front == -1) {
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements: ");
    for (int i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");
}

int main() {
    enqueue(1);
    enqueue(2);
    enqueue(3);
    enqueue(4);
    display();
    dequeue();
    dequeue();
    display();
    return 0;
}
```

The output for the above code is:

```
Queue elements: 1 2 3 4 
Dequeued element: 1
Dequeued element: 2
Queue elements: 3 4 
```

The program in this repository demonstrates the usage and implementation of queues.


