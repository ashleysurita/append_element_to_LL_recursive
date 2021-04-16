# append_element_to_LL_recursive

### Problem:
```class ListNode {
    constructor(value = 0, next = null) {
        this.value = value
        this.next = next
    }
}

function arrayify(head) {
    let ptr = head
    var array = []
    while (ptr) {
        array.push(ptr.value)
        
        ptr = ptr.next
    }
    return array
}

// 1 > 4 > 5
//         t

function append(head, target) {
   if(!head) return new ListNode(target)
   
    // if no head.next, it's the last element and append new node with target value
    if(head && !head.next) head.next = new ListNode(target)
    // keep looking for the last element
    else if(head && head.next) append(head.next, target)
        
    return head
}

// Test Cases
var LL1 = new ListNode(1, new ListNode(4, new ListNode(5)))
console.log(arrayify(append(null, 1))) // [1]
console.log(arrayify(append(LL1, 7))) // [1, 4, 5, 7]
console.log(arrayify(append(new ListNode(), 7))) // [0, 7]
