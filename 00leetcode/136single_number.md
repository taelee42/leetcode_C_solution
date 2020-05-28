[../](../)

[../README.md](../README.md)

```c
//Approach 1: List operation
/*
리스트 좀더 공부하고 다시보기
typedef struct  s_node
{
    int             content;
    struct s_node   *next;
}               t_node;

void            push(t_node **stack, int n)
{
    t_node  *new;
    
    new = (t_node *)malloc(sizeof(t_node));
    new->content = n;
    new->next = *stack;
    *stack = new;
}

void            pop(t_node **stack)
{
    t_node *temp;
    
    temp = (*stack)->next;
    free(*stack);
    *stack = temp;
}

void            print_stack(t_node *stack)
{
    t_node  *curr;
    
    curr = stack;
    while (curr)
    {
        printf("%d ", curr->content);
        curr = curr->next;
    }
    printf("\n");
}

int            search_pop(t_node **stack, int target)
{
    t_node  *curr;
    t_node  *temp;
    
    curr = *stack;
    while (curr)
    {
        if (curr->content == target)
        {
            temp = curr;
            curr = curr->next;
            free(curr);
            
        }
        curr = curr->next;
    }
}

int singleNumber(int* nums, int numsSize){
    t_node      *stack;
    int         i;
    
    stack = NULL;
    i = 0;
    while (i < numsSize)
    {
        
        i++;
    }
    

    return (0);
}
*/

//Approach 4: Bit Manipulation
/*i
int singleNumber(int* nums, int numsSize){
    int     i;
    int     ret;
    
    i = 0;
    ret = 0;
    while (i < numsSize)
    {
        ret ^= nums[i];
        i++;
    }
    return (ret);
}
*/
```

