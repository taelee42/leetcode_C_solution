

- #### Runtime: 0 ms, faster than 100.00% 

- #### Memory Usage: 6 MB, less than 100.00%

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */


bool* kidsWithCandies(int* candies, int candiesSize, int extraCandies, int* returnSize)
{
    bool    *can_greatest;
    int     max;
    int     i;
    
    *returnSize = candiesSize;
    can_greatest = (bool *)malloc(sizeof(bool) * candiesSize);
    max = candies[0];
    i = 1;
    while (i < candiesSize)
    {
        if (candies[i] > max)
            max = candies[i];
        i++; 
    }
    i = 0;
    while (i < candiesSize)
    {
        if (candies[i] + extraCandies >= max)
            can_greatest[i] = true;
        else
            can_greatest[i] = false;
        i++;
    }
    return (can_greatest);
}
```

