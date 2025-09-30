---
# 🧪 Experiment 19 :- Queue Implementation using Array in C++

---

## 📚 Theory

A **Queue** is a linear data structure that follows the **FIFO** principle — **First In, First Out**. This means the element inserted first will be removed first.

### 🔁 Queue Operations:
- **Enqueue**: Insert an element at the rear end.
- **Dequeue**: Remove an element from the front end.
- **Front**: View the front element without removing it.
- **isEmpty**: Check if the queue is empty.
- **isFull**: Check if the queue is full (for array-based implementation).

---

## ✅ Q1. Queue Using Class (With Array)

### 🔧 Syntax
class Queue {
private:
    int front, rear;
    int arr[MAX];
public:
    Queue();
    void enqueue(int value);
    void dequeue();
    void display();
};

---

🧠 Logic
Use an array to hold queue elements.
Maintain two indices: front and rear.
Initially, both are set to -1 indicating an empty queue.
For enqueue: Increment rear and insert the element.
For dequeue: Increment front to remove the element.
Handle overflow and underflow cases properly.

---

💻 Code
```cpp
#include <iostream>
using namespace std;

#define SIZE 100

class Queue {
private:
    int arr[SIZE];
    int front, rear;

public:
    Queue() {
        front = -1;
        rear = -1;
    }

    // Enqueue operation
    void enqueue(int value) {
        if (rear == SIZE - 1) {
            cout << "Queue Overflow!" << endl;
            return;
        }
        if (front == -1) front = 0; // First insertion
        arr[++rear] = value;
        cout << value << " enqueued to the queue." << endl;
    }

    // Dequeue operation
    void dequeue() {
        if (front == -1 || front > rear) {
            cout << "Queue Underflow!" << endl;
            return;
        }
        cout << arr[front++] << " dequeued from the queue." << endl;
    }

    // Display the queue
    void display() {
        if (front == -1 || front > rear) {
            cout << "Queue is empty!" << endl;
            return;
        }

        cout << "Queue elements: ";
        for (int i = front; i <= rear; i++) {
            cout << arr[i] << " ";
        }
        cout << endl;
    }
};

int main() {
    Queue q;

    q.enqueue(10);
    q.enqueue(20);
    q.enqueue(30);

    q.display();

    q.dequeue();
    q.display();

    return 0;
}
```

---

📌 Sample Output
10 enqueued to the queue
20 enqueued to the queue
30 enqueued to the queue

Queue elements: 10 20 30
10 dequeued from the queue

Queue elements: 20 30

---

✅ Conclusion
1. In this experiment, we learned:
2. How a Queue works using the FIFO concept.
3. How to implement a queue using a class and an array in C++.
4. How to handle overflow and underflow conditions.
5. The practical usage of queues in real-world applications like scheduling, buffering, etc.
This implementation builds a strong foundation for learning advanced topics such as circular queues and queues using linked lists or STL.

---
