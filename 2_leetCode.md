# 2.Add Two Numbers
* (<span style="color: orange"> Medium </span>)

You are given two non-empty linked lists representing two non-negative integers. The digits are stored in 
reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as 
a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

### example:
![](https://i.imgur.com/UaWdHzB.png)
![](https://i.imgur.com/SN9NGIs.png)

### constraints:
![](https://i.imgur.com/h4L1Qou.png)

### code:
```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */
struct ListNode* addTwoNumbers(struct ListNode* l1, struct ListNode* l2){
   struct ListNode *a = l1, *b = l2;
    
    int temp = 0; 
    while(a || b)
    {
        if (a && b){
            temp += (a -> val + b -> val);
            b = b -> next;
        } else if (a && ! b){
            temp += a -> val;
        } else if (!a && b){
            temp += b -> val;
            b = b -> next;
        }
        a -> val = temp % 10;
        temp -= a -> val;
        temp /= 10;
        
        if (!a -> next && (temp != 0 || b)){
            struct ListNode *c = (struct ListNode *)malloc(sizeof(struct ListNode));
            c -> val = 0;
            c -> next = NULL;
            a -> next = c;
        }
        a = a -> next;
    }
    return l1;
}

```

### submissions:
![](https://i.imgur.com/th8C6F3.png)
