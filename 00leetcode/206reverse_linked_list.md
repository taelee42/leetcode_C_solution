```c
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */

void    push(struct ListNode **stack, int val)
{
    struct ListNode *new;
    
    new = (struct ListNode *)malloc(sizeof(struct ListNode));
    new->val = val;
    new->next = *stack;
    *stack = new;
}

struct ListNode* reverseList(struct ListNode* head){
    struct ListNode *ret;
    
    ret = NULL;
    while (head)
    {
        push(&ret, head->val);
        head = head->next;
    }
    return (ret);
}
```