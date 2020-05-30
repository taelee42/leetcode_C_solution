```c
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     struct TreeNode *left;
 *     struct TreeNode *right;
 * };
 */

void isLeftLeaf(struct TreeNode *root, int *sum, int left)
{
    if (root == NULL)
        return ;
    if (!root->left && !root->right && left)
    {
        *sum += root->val;
        return ;
    }
    isLeftLeaf(root->left, sum, 1);
    isLeftLeaf(root->right, sum, 0);
}

int sumOfLeftLeaves(struct TreeNode* root){

    int sum;
    
    sum = 0;
    isLeftLeaf(root, &sum, 0);
    return (sum);
}
```

> Runtime: 0ms, faster than 100.00%
>
> Memory Usage: 6.1MB, less than 100.00%