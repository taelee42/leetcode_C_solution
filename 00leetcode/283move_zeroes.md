```c

//Approach 1
/*
void moveZeroes(int* nums, int numsSize){
    int     lastNonZeroFoundAt = 0;
    
    for (int i = 0; i < numsSize; i++)
    {
        if (nums[i] != 0)
            nums[lastNonZeroFoundAt++] = nums[i];
    }
   
    for (int i = lastNonZeroFoundAt; i < numsSize; i++)
    {
        nums[i] = 0;
    }
    
}
*/


```

12ms 85.62%
7.2MB, 100.00%

```c
//Approach 2
void    swap(int *a, int *b)
{
    int temp;
    
    temp = *a;
    *a = *b;
    *b = temp;
}

void moveZeroes(int* nums, int numsSize){
    int     lastNonZeroFoundAt = 0;
    
    for (int i = 0; i < numsSize; i++)
    {
        if (nums[i] != 0)
            swap(&nums[lastNonZeroFoundAt++], &nums[i]);
    }
   
 
}
```

