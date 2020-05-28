Runtime: 24 ms, faster than 86.03% of C online submissions for Merge Two Binary Trees.
Memory Usage: 14.4 MB, less than 100.00% of C online submissions for Merge Two Binary Trees.

```c
// Approach 1

struct TreeNode* mergeTrees(struct TreeNode* t1, struct TreeNode* t2){
    
    if (!t2)
        return (t1);
    if (!t1)
        return (t2);
    t1->val += t2->val;
    t1->left = mergeTrees(t1->left, t2->left);
    t1->right = mergeTrees(t1->right, t2->right);
    
    return (t1);
    
}

```



28ms // 58.10%
20.2MB// 33.33%

```c
// Approach 2
struct TreeNode* mergeTrees(struct TreeNode* t1, struct TreeNode* t2)
{
    struct TreeNode     *node;
    
    if (!t1 && !t2)
        return (NULL);
    if (!t2)
        return (t1);
    if (!t1)
        return (t2);
    node = (struct TreeNode *)malloc(sizeof(struct TreeNode));
    node->val = t1->val + t2->val;
    node->left = mergeTrees(t1->left, t2->left);
    node->right = mergeTrees(t1->right, t2->right);
    return (node);
}
```



위의 트리 프린트하는 함수 만들기

```c
//실패한 코드, 트리 프린트하는거 알아보기
/*
void    print_node(struct TreeNode *tree)
{
    print_node(&tree->left);
    printf("%d",tree->val);
	print_node(&tree->right);
}
*/
```





https://www.geeksforgeeks.org/merge-two-binary-trees-node-sum/