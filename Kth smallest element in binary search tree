#include <iostream>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

int kthSmallest(TreeNode* root, int& k) {
    if (!root) return -1;
    int left = kthSmallest(root->left, k);
    if (k == 0) return left;
    k--;
    if (k == 0) return root->val;
    return kthSmallest(root->right, k);
}

int main() {
    TreeNode* root = new TreeNode(3);
    root->left = new TreeNode(1);
    root->left->right = new TreeNode(2);
    root->right = new TreeNode(4);
    
    int k = 2;
    cout << "Kth Smallest: " << kthSmallest(root, k) << endl;
    return 0;
}
