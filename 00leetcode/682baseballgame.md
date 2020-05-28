Runtime: 4 ms, faster than 91.30% of C online submissions for Baseball Game.

Memory Usage: 6.1 MB, less than 100.00% of C online submissions for Baseball Game.

```c

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

void            print_stack(t_node  *stack)
{
    t_node *curr;
    
    curr = stack;
    while (curr != NULL)
    {
        printf("%d ", curr->content);
        curr = curr->next;
    }
    printf("\n");
}
int             sum_stack(t_node *stack)
{
    t_node *curr;
    int     sum;
    
    sum = 0;
    curr = stack;
    while (curr != NULL)
    {
        sum += curr->content;
        curr = curr->next;
    }
    return (sum);
}

int calPoints(char ** ops, int opsSize)
{
    
    t_node  *stack;
    int     i;
    
    stack = NULL;
    i = 0;
    while (i < opsSize)
    {
        if (*ops[i] == '+')
            push(&stack, stack->content + stack->next->content);
        else if (*ops[i] == 'D')
            push(&stack, stack->content * 2);
        else if (*ops[i] == 'C')
            pop(&stack);
        else
            push(&stack, atoi(ops[i]));
        i++;
    }
    return (sum_stack(stack));
}
```

