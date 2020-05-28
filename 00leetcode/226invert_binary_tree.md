## Approach 1: reculsive

```c

struct TreeNode* invertTree(struct TreeNode* root){
    struct TreeNode* left;
    struct TreeNode* right;
    
    if (root == NULL)
        return (NULL);
    left = invertTree(root->left);
    right = invertTree(root->right);
    root->left = right;
    root->right = left;
    return (root);
}
```

> Runtime: 0ms, faster than 100.00%
>
> Memory Usage: 5.2MB, less than 100.00%



## Approach 2: iterative



공부하고 다시와야할듯