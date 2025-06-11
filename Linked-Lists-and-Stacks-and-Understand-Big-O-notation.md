### Understanding Algorithm
![images](Images/Screenshot%202025-06-11%20145301.png)

# A linked list is a linear data structure where elements (called nodes) are not stored in contiguous memory like arrays.
Each node contains:

Data
A reference (or pointer) to the next node in the list.


Linked lists are created to overcome limitations of arrays, especially:
Dynamic size: No need to define a fixed size like arrays.
Efficient insertions/deletions: Especially at the beginning/middle—no shifting like arrays.

## Real Uses
![RealUSES](Images/Screenshot%202025-06-11%20150458.png)

Memory management – OS uses linked lists for tracking memory blocks.
Implementing stacks and queues – easier using linked lists.

##✅ Advantages of Linked Lists over Arrays
| Feature                               | Linked List                      | Array                             |
| ------------------------------------- | -------------------------------- | --------------------------------- |
| **Size**                              | Dynamic                          | Fixed                             |
| **Insert/Delete at beginning/middle** | Fast (O(1)/O(n))                 | Slow (O(n))                       |
| **Memory usage**                      | Efficient for large dynamic data | May waste/overuse memory          |
| **No memory shifting**                | Yes                              | Shifting needed for insert/delete |
| **Flexibility**                       | Easy to grow/shrink              | Difficult (need to reallocate)    |

##❌ Disadvantages of Linked Lists
| Issue                         | Explanation                                                |
| ----------------------------- | ---------------------------------------------------------- |
| **Slow access time**          | To access the 5th element, you must go node by node (O(n)) |
| **Extra memory**              | Each node stores a pointer, using more memory than arrays  |
| **No random access**          | Unlike arrays, you can’t jump directly to an index         |
| **More complex to implement** | More code and care needed for insertion, deletion, etc.    |


```python
# Define a Node
class Node:
    def __init__(self, data):
        self.data = data         # Store the data (value) in the node
        self.next = None         # Pointer to the next node in the list (initially None)

# Define a Linked List
class LinkedList:
    def __init__(self):          
        self.head = None         # Initialize the head of the list as None (empty list)

    def append(self, data):      # Method to add a new node at the end of the list
        new_node = Node(data)    # Create a new node with the given data
        if not self.head:        # If the list is empty (head is None)
            self.head = new_node # Make the new node the head of the list
            return               # Exit the function
        temp = self.head         # Start from the head
        while temp.next:         # Traverse to the end of the list
            temp = temp.next     # Move to the next node
        temp.next = new_node     # Link the last node to the new node

    def display(self):           # Method to print the linked list
        temp = self.head         # Start from the head
        while temp:              # Traverse until the end (None)
            print(temp.data, end=" → ")  # Print the data followed by an arrow
            temp = temp.next     # Move to the next node
        print("None")            # Print None to indicate end of list
  

# Example usage
ll = LinkedList()        # Create a new LinkedList object
ll.append(10)            # Add 10 to the list
ll.append(20)            # Add 20 to the list
ll.append(30)            # Add 30 to the list
ll.display()             # Print the contents of the list


```

