## Approach 1 : recursive

```c
struct TreeNode* searchBST(struct TreeNode* root, int val){
    if (root == NULL || root->val == val)
        return (root);
    if (root->val > val)
        return (searchBST(root->left, val));
    else
        return (searchBST(root->right, val));
}
```

> Runtime : 24 ms, faster than 78.41%
> Memory Usage: 14.9MB, less than 100.00%



## Approach 2 : iterative

```c
struct TreeNode* searchBST(struct TreeNode* root, int val){
    while (root != NULL && root->val != val)
    {
        if (root->val > val)
            root = root->left;
        else
            root = root->right;
    }
    return (root);
}
```
> Runtime: 24ms, faster than 78.41%
>
> Memory Usage: 15MB, less than 100.00%
