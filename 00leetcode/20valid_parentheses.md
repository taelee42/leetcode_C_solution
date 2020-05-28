
```c
typedef struct s_node
{
    char           data;
    struct s_node  *next;
}               t_node;

void    push(t_node **stack, char data)
{
    t_node  *new;

    new = (t_node *)malloc(sizeof(t_node));
    new->data = data;
    new->next = *stack;
    *stack = new;
}

char    pop(t_node **stack)
{
    t_node  *temp_node;
    char    temp_data;

	if (*stack == NULL)
	{
		printf("Cannot pop from zero stack\n");
		exit(0);
	}

    temp_node = *stack;
    temp_data = (*stack)->data;
    *stack = (*stack)->next;
    free(temp_node);
    return (temp_data);
}

void    print_stack(t_node *stack)
{
    t_node *curr;

    if (stack == NULL)
    {
        printf("Cannot pop from zero stack");
    }
    curr = stack;
    while (curr != NULL)
    {
       printf("%c -> ", curr->data);
       curr = curr->next;
    }
    printf("\n");
}

bool isValid(char * str){
    t_node  *stack;
    int     i;
    char    s;

    stack = NULL;
    i = 0;
    while (i < strlen(str))
    {
        if (str[i] == '(' || str[i] == '{' || str[i] == '[')
        {
            push(&stack, str[i]);
        }
        else
        {
            if (stack == NULL)
                return (false);
            s = pop(&stack);
            if (str[i] == ')')
			{
                if (s != '(')
                    return (false);
			}
            else if (str[i] == '}')
			{
                if (s != '{')
                    return (false);
			}
            else if (str[i] == ']')
			{
                if (s != '[')
                    return (false);
			}
        }
    i++;
    }
    if (stack == NULL)
		return (true);
	else
    	return (false);
}
```