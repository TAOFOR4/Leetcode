```
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     struct TreeNode *left;
 *     struct TreeNode *right;
 * };
 */

bool solve(struct TreeNode* root1, struct TreeNode* root2)
{
    if (root1 == NULL && root2 == NULL) return true;
    if (root1 == NULL || root2 == NULL) return false;
    if (root1->val != root2->val) return false;

    //separated these calls just for clarification
    //return (solve(root1->left, root2->right) && solve(root1->right, root2->left)); would also work
    bool leftRightMatch = solve(root1->left, root2->right);
    bool rightLeftMatch = solve(root1->right, root2->left);
    return (leftRightMatch && rightLeftMatch);

}
bool isSymmetric(struct TreeNode* root) 
{
    return solve(root->left, root->right);
}
```