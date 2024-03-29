# LeetCode_Note
This github repository is used to document the common leetcode questions that shows up in typical coding interviews. I usually do summary and reviews and commit to this repository once a week.

Programming Language: **JavaScript** <br>
Topics: strings, arrays, linked list, hash tables, stacks, queue, tree, graph

## 2181. Merge Nodes in Between Zeros (Linked list - medium difficulty)

Try not to use array, since it costs extra space
```
var mergeNodes = function(head) {
    
    // create a dummyNode as the final output. A dummy node has a huge performance gain compared to an array.
    let dummyNode = {val:null, next:null};
    let tail = dummyNode;
    
    let currNode = head.next;
    
    let sum = 0;
    
    while(currNode){
          
        if (currNode.val == 0) {
            
            let newNode = new ListNode(sum);
            tail.next = newNode;
            tail = tail.next;
            sum = 0;
            
        } else if (currNode.val != 0) {
                   
            sum = sum + currNode.val;
        }
        
        currNode = currNode.next;
    }
    
    // return dummyNode.next as the head node.
    return dummyNode.next;
    
};
```

## 485. Max Consecutive Ones (Array - easy)
compare and overwrite
```
var findMaxConsecutiveOnes = function(nums) {
    
    let count = 0;
    let max = 0;
    
    for (let i = 0; i<nums.length; i++) {
        
        if (nums[i] == 1) {
            
            count = count + 1;
            
        } else if (nums[i] == 0) {
            
            count = 0;
        };
        
        max = Math.max(max,count);
        
    }
    
    return max;
    
};
```

## 1475. Final Prices With a Special Discount in a Shop
use brute force. O(n^2) with nested for loop

```
var finalPrices = function(prices) {
    
    for (let i=0; i<prices.length;i++) {
        
        let discount;
        
        for (let j = i+1; j<prices.length; j++) {
            
            if (prices[j] <= prices[i]) {
                
                discount = prices[j];
                break;
            }
        }
        
        if (discount) {
            
            prices[i] = prices[i] - discount;
        }
        
    }
    
    return prices;
    
};
```

![Alt text](./smallerThanAll.JPG?raw=true "Title")
looooooooooooooooooooool

## 206. Reverse Linked List
simple question. Simply change the direction of pointers iteratively, until the head reach the end of the nodelist.
```
var reverseList = function(head) {
    
    let prev = null;
    
    while (head) {
        let next = head.next;
        head.next = prev;
        prev = head;
        head = next;
    }
  
    return prev;
};

```
## 232. Implement Queue using Stacks

Do something no the push method, rather than then pop method
```
var MyQueue = function() {
    
    this.s1 = [];
    this.s2 = [];
};

/** 
 * @param {number} x
 * @return {void}
 */
MyQueue.prototype.push = function(x) {
    
    while (this.s1.length) {
           
           this.s2.push(this.s1.pop())
    };
    
    this.s1.push(x);
    
    while (this.s2.length) {
           
           this.s1.push(this.s2.pop())
    }
};

/**
 * @return {number}
 */
MyQueue.prototype.pop = function() {
    
    return this.s1.pop();
    
};

/**
 * @return {number}
 */
MyQueue.prototype.peek = function() {
    
    return this.s1[this.s1.length - 1];
};

/**
 * @return {boolean}
 */
MyQueue.prototype.empty = function() {
    
    return this.s1.length == 0;
};
```

## 387. First Unique Character in a String
2 approaches: indexOf()&lastIndexOf() and hashMap
```
var firstUniqChar = function(s) {
   for(i=0;i<s.length;i++){
       if (s.indexOf(s[i])===s.lastIndexOf(s[i])){
          return i;
      } 
   }
   return -1;
};
```
hashMap approach:
```
 var firstUniqChar = function(s) 
    var map=new Map();
    for(i=0;i<s.length;i++){
         if(map.has(s[i])){
             map.set(s[i],2);
         }
         else{
             map.set(s[i],1);
         }
     }

    for(i=0;i<s.length;i++){
        if(map.has(s[i]) && map.get(s[i])===1){
            return i;
        }
    }
    return -1;
 } ;
```

## 104. Maximum Depth of Binary Tree
```
var maxDepth = function(root) {
    
    if (!root) {return 0};
        
    return 1 + Math.max( maxDepth(root.left) , maxDepth(root.right) ) ;
```

## 9. Palindrome Number
First approach: convert the number into string and use two pointers technique \
Second approach: a mathematical approach, without converting the number into a string
```
var isPalindrome = function(x) {
    
    // Palindrome: read the same from left->right and right->left
    
    // use a mathematical approach:
    
    if (x < 0) {return false}
    
    let div = 1;
    
    while (x >= 10*div) {
           
         div = div*10;       
    }
    
    while (x) {
          
        let left = Math.floor(x/div);
        let right = x%10 ;
        
        if (left != right) {return false}
        
        x = Math.floor( (x%div)/10 );
        div = div/100;
    }
        
    return true;
};
```
