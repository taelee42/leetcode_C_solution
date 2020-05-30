

```c
char * defangIPaddr(char * address){
    int     i;
    int     j;
    int     dot_number;
    int     ret_size;
    char    *ret;
    
    dot_number = 0;
    i = 0;
    while (address[i])
    {
        if (address[i] == '.')
            dot_number++;
        i++;
    }
    ret_size = i + 2 * dot_number;
    ret = malloc(sizeof(char) * (ret_size + 1));
    
    i = 0;
    j = 0;
    while (i < ret_size)
    {
        if (address[j] == '.')
        {
           ret[i++] = '[';
           ret[i++] = '.';
           ret[i++] = ']';
            j++;
        }
        else
        {
            ret[i] = address[j];
            i++; 
            j++;
        }
    }
    ret[i] = '\0';
    return (ret);
}
```

> Runtime: 0ms, faster than 100.00%
>
> Memory Usage: 5.2MB, less than 100.00%