# LeetCode_notes

## Some things to remember:

- Complexity ranking: n! -> 2^n -> n^3 -> n^2 -> nlog(n) -> n -> sqrt(n) -> log(n) -> constant  

- Remainder:
    - ASK for clarification first, don't jump into code right away
    - THINK OUT LOUD!! Say your thinking process while coding

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
  
- INTERVAL typle problem:
  - make sure to know how to merge 2 overlapping intervals: take the min. of 2 left endpoints, and the max. of 2 right endpoints:
  
  ```
    // merge 2 intervals
    newInterval[0] = Math.min(newInterval[0], currInterval[0]);
    newInterval[1] = Math.max(newInterval[1], currInverval[1]);
  ```
  
- String
  - String is immutable
  - Use StringBuilder class in Java to create a new string; return sb.toString() at the end
  
  ```
    StringBuilder sb = new StringBuilder();
  
    .... do things ....
  
    return sb.toString();
  ```
  
- Linked List
  - 3 types of linked list: 
    -   singly
    -   double  
    -   cycle linkedlist
        - Floyd's Algorithm: find the intersection - slow and fast pointer, when slow & fast meet, reset a new pointer at the start, move 2 pointers at the same pace; when they meet each other, then there is the intersection
        
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
        
    - A special kind of tree: trie - prefix tree (autocomplete, spellchecker)
        - has a mapping instead of left/right pointer
        - commonly used in word search
        
- Graph: (V-Vertex(Node), E-Edges)
    - 2 common types of Graph: directed graph vs undirected graph
    - 2 ways to represent a graph:
        - Adjacency Matrix:
            - An 2d array to store 1's/0's to represent edges
            - T.C: O(1) S.C: O(v^2)
        - Adjacency List:
            - An array/arrayList of LinkedList. Each linkedList has a unique node at the head. All adjacent neighbors to that node are added to that node's linkedList;
            - T.C: O(V) S.C: O(V+E)
    - Some common graph search algorithm:
        - BFS & DFS
        - Union Find
          - Usually define 2 seperate find && union methods
            
        - Topological sort (an implementation of DFS)
        - Prims Algorithm (to generate a tree (MST Min spanning tree) from a graph)
        - Dijsktra Algorithm (find the shortest path from a graph, an implementation of BFS)
