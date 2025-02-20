# Introduction to Linked Lists

## What is a Linked List?  
A **linked list** is a linear data structure where elements (nodes) are linked using pointers. Unlike arrays, elements in a linked list are **not stored in contiguous memory locations**.

Each node consists of:  
- **Data** (the actual value stored)  
- **Pointer** (address of the next node)

## Why Use Linked Lists Instead of Arrays?  
✅ **Dynamic Size:** Linked lists can grow/shrink dynamically, unlike arrays.  
✅ **Efficient Insertions/Deletions:** No need to shift elements.  
✅ **Memory Utilization:** Uses memory as needed.  

However, linked lists use **extra memory** for pointers and have **slower access times** than arrays.

## Types of Linked Lists  
1. **Singly Linked List:** Each node points to the next node.  
2. **Doubly Linked List:** Nodes have pointers to both previous and next nodes.  
3. **Circular Linked List:** The last node points back to the first node.

---

## **📝 Example: Singly Linked List in Python**
```python
# Define a node class
class Node:
    def __init__(self, data):
        self.data = data  # Store data
        self.next = None  # Pointer to next node

# Define a LinkedList class
class LinkedList:
    def __init__(self):
        self.head = None  # Initialize empty list

    # Insert a node at the end
    def append(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        temp = self.head
        while temp.next:
            temp = temp.next
        temp.next = new_node

    # Print the linked list
    def display(self):
        temp = self.head
        while temp:
            print(temp.data, end=" -> ")
            temp = temp.next
        print("None")

# Usage
ll = LinkedList()
ll.append(10)
ll.append(20)
ll.append(30)
ll.display()  # Output: 10 -> 20 -> 30 -> None

