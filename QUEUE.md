# Queue

A queue follows the FIFO (First In First Out) principle. 

## Operations

- **Enqueue**: Add an item to the queue through the rear.
- **Dequeue**: Remove an item from the queue through the front.

## Methods

1. **isempty()**: Determines if the queue is empty.
2. **isfull()**: Determines if the queue is full.
3. **front()**: Returns the element that is at the front of the queue.
4. **enqueue()**: Inserts an element to the rear of the queue.
5. **dequeue()**: Removes an element from the front of the queue.

## Types of Queues

- **Simple Queue**: Enqueue() in rear and Dequeue() in front.
- **Circular Queue**: Has limited length and the front is connected to the rear, the data overrides in case of overflow.
- **Priority Queue**: Sorts elements based on a certain priority and inserts them into the queue.
- **Dequeue (Double Ended Queue)**: Can add or remove an element from both the front and rear.

## How to Check if Queue is Empty or Not

1. When front = -1 & rear = -1
2. When front = rear + 1