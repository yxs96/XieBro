## 二叉树刷题
1.快速排序相单于二叉树的前序遍历  
2.归并排序相当于二叉树的后序遍历 

### 226.翻转二叉树
```C++
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    TreeNode* invertTree(TreeNode* root) {
        if (root == NULL)
            return NULL;
        
        TreeNode* tmp = root->left;
        root->left = root->right;
        root->right = tmp;

        invertTree(root->left);
        invertTree(root->right);

        return root;
    }
};
```


### 116.填充每个节点的下一个右侧节点指针
```C++
/*
// Definition for a Node.
class Node {
public:
    int val;
    Node* left;
    Node* right;
    Node* next;

    Node() : val(0), left(NULL), right(NULL), next(NULL) {}

    Node(int _val) : val(_val), left(NULL), right(NULL), next(NULL) {}

    Node(int _val, Node* _left, Node* _right, Node* _next)
        : val(_val), left(_left), right(_right), next(_next) {}
};
*/

class Solution {
public:
    // 主函数
    Node* connect(Node* root) {
        if (root ==NULL)    return NULL;

        connectTwoNode(root->left, root->right);
        return root;
    }
    
    // 定义：输入两个节点，将它俩连接起来
    void connectTwoNode(Node* node1, Node* node2){
        if (node1==NULL || node2==NULL)
            return;
        /**** 前序遍历位置 ****/
        // 将传入的两个节点连接
        node1->next = node2;
        
        // 连接相同父节点的两个子节点
        connectTwoNode(node1->left, node1->right);
        connectTwoNode(node2->left, node2->right);
        // 连接跨越父节点的两个子节点
        connectTwoNode(node1->right, node2->left);
    }
};

```

### 114.二叉树展开为链表
```C++
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    // 定义：将以 root 为根的树拉平为链表
    void flatten(TreeNode* root) {
        // base case
        if(root == NULL)    return;
        
        /**** 后序遍历位置 ****/
        // 1、左右子树已经被拉平成一条链表
        flatten(root->left);
        flatten(root->right);
        
        // 2、将左子树作为右子树
        TreeNode* left = root->left;
        TreeNode* right = root->right;

        root->left = NULL;
        root->right = left;

        // 3、将原先的右子树接到当前右子树的末端
        TreeNode* p = root;
        while(p->right!=NULL){
            p = p->right;
        }
        p->right = right;
    }
};
```





















