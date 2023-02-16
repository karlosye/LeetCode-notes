# LeetCode_notes

## Some things to remember:

- Complexity ranking: n! -> 2^n -> n^3 -> n^2 -> nlog(n) -> n -> sqrt(n) -> log(n) -> constant  

- Misc:
    - Be aware of int(Integer) overflow; when dealing with very large number, use Long instead (64bit > 32bit)
    - When dividing between 2 integer values, in order to get decimal, cast one of the divisor to double --> JAVA by default implements integer division
    - Be aware of primitive type vs wrapper class  --> **E.g Integer vs int, Boolean vs boolean**

- Array:
  - Time & Space complexity of sorting algorithem
  - Two pointers technique
  - Matrix: mostly simulation - ability to write for loop and while loop
  - converting between list and static array
  - when initialize an int array in Java, the default item value will be set to 0
  
- String
  - String is immutable
  - Use StringBuilder class in Java to create a new string; return sb.toString() at the end
  
  ```
    StringBuilder sb = new StringBuilder();
  
    .... do things ....
  
    return sb.toString();
  ```
  
- Linked List
  - 3 types of linked list: singly, double, cycle linkedlist
  - Pointers manipulation
  - when dealing with the first linked list node, use a dummyNode
 
- Heap:
  - By default, Java creates minHeap (smaller number has a higher priority)
  - Heap is NOT a sorted list!!!!
  - remove/add takes O(log(n))
  - make sure you spell PriorityQueue correctly
  
 ```
    PriorityQueue<Integer> minPQ = new PriorityQueue<>();
    PriorityQueue<Integer> maxPQ = new PriorityQueue<>((n1,n2) -> n2 - n1);
 ```

 - Stack & Queue:
    - In JAVA, stack is a class, queue is an interface (use LinkedList or Dequeue or ArrayList)
    - When implementing a queue in Java, Deque is preferred over linkedList because Dequeue takes less memory

- HashTable:
   - Implementation: array + linkedList (easy lookup + easy change)
   - process: key -> hashCode (via some hash function) -> inbound index -> find the value (deal with hash collision such as chained linked list)
   - assume the lookup time is constant (assume we have very good hash function and no hash collision)
   - A good way to deal with duplicate number or character: hashSet
   
   ```
    Set<Character> charSet = new HashSet<>();
    // do something ...
   ```
       
- Dynamic Programming:
    - The usual approach: 
        - brute force dfs --> dfs with a cache (either array or hashMap) -> bottom-up dynamic programming
        - make sure to communicate the optimization process with the interviewer
    - Major question series:
        - Basic ones
        - Climb Stairs + Jump Game series
        - Trade stock series
        - Rob houses series
    - Major patterns: (!important)
        - Fib numbers
        - 0/1 KnapSack
        - Unbounded KnapSack
        - Largest common subsequence
        - Palindromes
     - Make sure to understand the following DP patterns and related questions:
        - https://docs.google.com/spreadsheets/d/1pEzcVLdj7T4fv5mrNhsOvffBnsUH07GZk7c2jD-adE0/edit#gid=0

- Bit manipulation:
    - XOR: **1** if two ints are different, **0** if two ints are the same
    - 0 XOR anything = anything, anything XOR anything itself = 0
    - 5 ^ 5 = 0, 5 ^ 0 = 5
    
- Tree:
    - inOrder vs preOrder vs postOrder
    - Binary Tree vs Binary Search Tree
    - BST:
        - note that an in-order traversal on BST is sorted 
        - when search a node in BST, if node.val < key -> node = node.right (search to the right); vice versa
        
    - A special kind of tree: trie - prefix tree
        - has a mapping instead of left/right pointer
        - commonly used in word search
