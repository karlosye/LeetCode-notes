# LeetCode_Journal
This github repository is used to document the common leetcode questions that shows up in typical coding interviews. I usually do summary and reviews and commit to this repository once a week.

## 2181. Merge Nodes in Between Zeros
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
