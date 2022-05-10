# LeetCode_Journal

```
var mergeNodes = function(head) {
    
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
    
    
    return dummyNode.next;
    
};
```
