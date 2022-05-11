# LeetCode_Journal
This github repository is used to document the common leetcode questions that shows up in typical coding interviews. I usually do summary and reviews and commit to this repository once a week.

Programming Language: JavaScript
Topics: strings, arrays, linked list, stacks, queue, tree, graph

## 2181. Merge Nodes in Between Zeros (Linked list - medium difficulty)
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
