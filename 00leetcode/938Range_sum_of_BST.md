## Approach 1: Reculsive

```c

int rangeSumBST(struct TreeNode* root, int L, int R){
   if (root == NULL) 
       return (0);
    else if (root->val >= L && root->val <= R)
       return (root->val + rangeSumBST(root->left, L, R) + rangeSumBST(root->right, L, R)) ;
    else
        return (rangeSumBST(root->left, L, R) + rangeSumBST(root->right, L, R));
}
```

>Runtime: 84ms, faster than 67.79%
>
>Memory Usage: 42.1MB, less than 100.00%

## Approach 2: Iterative

```c
int rangeSumBST(struct TreeNode* root, int L, int R){
    int      sum;
    
    sum = 0;
    while (root != NULL) 
    {
        if (root->val >= L && root->val <= R)
            sum += root->val;
        if (root->val < L)
            root = 
    }
}
```

실패함. 모르겠음