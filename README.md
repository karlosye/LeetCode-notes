# LeetCode_notes

Some things to remember:

- Misc:
    - Be aware of int(Integer) overflow; when dealing with very large number, use Long instead

- Array:
  - Time & Space complexity of sorting algorithem
  - Two pointers technique
  - Matrix: mostly simulation - ability to write for loop and while loop
  - converting between list and static array
  
- String
  - String is immutable
  - Use StringBuilder class in Java to create a new string; return sb.toString() at the end
  
- Linked List
  - 3 types of linked list: singly, double, cycle linkedlist
  - Pointers manipulation
  - when dealing with the first linked list node, use a dummyNode
 
- Heap:
  - By default, Java creates minHeap (smaller number has a higher priority)
  - Heap is NOT a sorted list!!!!
  - remove/add takes O(log(n))

 - Stack & Queue:
    - In JAVA, stack is a class, queue is an interface (use LinkedList or Dequeue or ArrayList)
