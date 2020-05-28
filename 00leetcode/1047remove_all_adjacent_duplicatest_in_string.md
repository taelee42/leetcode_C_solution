```c
//제출코드
int     check_duplicates(char **arr, long *len)
{
    long i;
    long j;
    int is_duplicates;
    
    is_duplicates = 0;
    i = 0;
    while (i < *len - 1)
    {
        if ((*arr)[i] == (*arr)[i + 1])
        {
            //(*arr)[i] = (*arr)[i + 2];
            //(*arr)[i + 1] = (*arr)[i + 3];
            memmove(*arr + i, *arr + i + 2, *len - i - 2);
            (*arr)[*len - 1] = '\0';
            (*arr)[*len - 2] = '\0';
            *len -= 2;
            is_duplicates = 1;
            //printf("%s\n", *arr);
            break ;
        }
        i++;
    }
    return (is_duplicates);
}
char * removeDuplicates(char * S)
{
    long        len;
    char        *arr;
    
    len = strlen(S);
    arr = strdup(S);
    
    while (1)
    {
        if(!check_duplicates(&arr, &len))
            break;
    }
    
    return (arr);
}
```
---

```c
//실패코드
typedef struct s_node
{
    char            data;
    struct s_node   *next;
}               t_node;

void            push(t_node **stack, char data)
{
    t_node  *new;
    
    new = (t_node *)malloc(sizeof(t_node));
    new->data = data;
    new->next = *stack;
    *stack = new;
}

char            pop(t_node **stack)
{
    char    temp_data;
    t_node  *temp_node;
    
    temp_data = (*stack)->data;
    temp_node = *stack;
    *stack = (*stack)->next;
    free(temp_node);
    return (temp_data);
    
}


void            print_stack(t_node *stack)
{
    t_node  *curr;
    
    curr = stack;
        while (curr)
    {
        printf("%c ->", curr->data);
        curr = curr->next;
    }
    printf("\n");
}

void            check_duplicates(t_node **stack)
{
    t_node  *curr;
    t_node  *temp1;
    t_node  *temp2;
    
    curr = *stack;
    while (curr)
    {
        if (curr->data == curr->next->data)
        {
            temp1 = curr;
            temp2 = curr->next;
            //여기 하는중이었음
        }
            
    }
}

char * removeDuplicates(char * S)
{
    t_node  *stack;
    int i;
   
    stack = NULL;
    i = 0;
    while (i < strlen(S)
    {
        push(&stack, S[i])
    }
    
    
    
   
    
    return ("abc");
}
```



- 위처럼 하고 있었는데 굳이 스택으로 풀어야하나 하는 의문을 갖게됨.

- 배열로 순회해서 풀어보기

- 배열로 풀려니 한개가 앞부분의 nod가 pop될때 그 이후의 node전부를 옮겨줘야하는 불상사가 일어남

  memmove로 해결하긴 했지만 배열의 나머지 부분을 '\0'으로 채웠기 때문에 메모리를 많이 쓸듯
  이래서 stack을 쓰는게 아닌가 싶음. 

- 배열의 단점이 초기 사이즈를 지정해줘야 하는데 처음에 내가 int로 설정해놨더니 엄청 긴 문자열이 들어왔을때 문제가 생겨서 type을 long으로 바꿔주어 해결하였다. 이런점도 배열의 단점인듯 하다.



