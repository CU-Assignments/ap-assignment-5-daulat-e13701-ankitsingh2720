#include <iostream>
#include <vector>
#include <unordered_map>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

unordered_map<int, int> inorderIndexMap;

TreeNode* build(vector<int>& inorder, vector<int>& postorder, int& postIdx, int left, int right) {
    if (left > right) return NULL;
    int rootVal = postorder[postIdx--];
    TreeNode* root = new TreeNode(rootVal);
    int index = inorderIndexMap[rootVal];
    root->right = build(inorder, postorder, postIdx, index + 1, right);
    root->left = build(inorder, postorder, postIdx, left, index - 1);
    return root;
}

TreeNode* buildTree(vector<int>& inorder, vector<int>& postorder) {
    int postIdx = postorder.size() - 1;
    for (int i = 0; i < inorder.size(); ++i)
        inorderIndexMap[inorder[i]] = i;
    return build(inorder, postorder, postIdx, 0, inorder.size() - 1);
}

void inorderPrint(TreeNode* root) {
    if (!root) return;
    inorderPrint(root->left);
    cout << root->val << " ";
    inorderPrint(root->right);
}

int main() {
    vector<int> inorder = {9, 3, 15, 20, 7};
    vector<int> postorder = {9, 15, 7, 20, 3};
    TreeNode* root = buildTree(inorder, postorder);
    inorderPrint(root);
    return 0;
}
