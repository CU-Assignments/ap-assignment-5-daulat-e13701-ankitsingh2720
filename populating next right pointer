#include <iostream>
using namespace std;

struct Node {
    int val;
    Node* left;
    Node* right;
    Node* next;
    Node(int x) : val(x), left(NULL), right(NULL), next(NULL) {}
};

Node* connect(Node* root) {
    if (!root) return NULL;
    Node* leftmost = root;
    while (leftmost->left) {
        Node* head = leftmost;
        while (head) {
            head->left->next = head->right;
            if (head->next) head->right->next = head->next->left;
            head = head->next;
        }
        leftmost = leftmost->left;
    }
    return root;
}

void printNext(Node* root) {
    while (root) {
        Node* temp = root;
        while (temp) {
            cout << temp->val << "->";
            temp = temp->next;
        }
        cout << "NULL" << endl;
        root = root->left;
    }
}

int main() {
    Node* root = new Node(1);
    root->left = new Node(2);
    root->right = new Node(3);
    root->left->left = new Node(4);
    root->left->right = new Node(5);
    root->right->left = new Node(6);
    root->right->right = new Node(7);

    connect(root);
    printNext(root);
    return 0;
}
