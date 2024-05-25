# Tree - Concept and Implementation

In any tree with N number of nodes there are maximum N - 1 number of edges. A node that doesn't have any child nodes is called a "LEAF" or "TERMINAL" or "EXTERNAL" node. The degree of a node is the number of children that that node has. The level is kinda like the floor on which the node is at, the root node is at level 0. The total number of edges from a leaf node to a particular node is called as the height of that particular node. (The height of the root node is the height of the tree.) The total number of edges from the root node to the particular node is called as the depth of that node. ( The depth of the tree: number of edges from root to the leaf node.) The sequence of nodes and edges from one node to another node is called as the path between that two nodes. The connection of nodes that will be formed by a node is called a sub-tree of that node.

## Types of Trees

### General Tree

- Each node can have infinite children
- Root has 0 in-degrees and infinite out-degrees
- Height: the length of the longest path from the root to leaf of the tree ( edges + 1)

### Binary Tree

- Max two children ( left and right )
- Root has 0 in-degrees and 2 out-degrees
- Each node has max 1 in-degree and 2 out-degree
- Height(T) = {max(height(leftchild), height(right child) + 1}

#### Array representation

- The nodes are marked sequentially from left to right
- The first array location has the number of nodes inside the tree

#### Linked-list representation

- More efficient than array
- The left pointer holds the address of the left child the right pointer holds the value of right child.

### Binary Tree types

#### Extended Binary tree

- Has "special nodes" or "failure nodes" instead of null subtree.
- Is transformed version of any binary tree
- Nodes from original tree are the internal nodes
- "Special nodes" are the external nodes

#### Complete Binary Tree

- All leaf nodes are at level n or n - 1 
- Levels are filled from left to right

#### Full binary Tree 

- Sometimes called "proper binary tree" or "2 - tree"
- Every node other than leaf nodes have two or no children 
- Every level is completely filled up
- Number of nodes: 2**(h + 1) - 1 

#### Skewed binary tree

- Every node in the tree contains either only left or only right sub trees.
- Left-skewed binary tree
- Right-skewed binary tree

#### Strictly binary tree

- A tree will have either two or no child at all

#### Expression binary tree

- Used to evaluate certain expressions
- Common types: algebraic or binary expression tree
- Can represent both unary and binary operations
- The leaf nodes are operands or variables and the other nodes are expressions.
- Often used in compilers

### Binary Tree traversal

Binary search tree properties (BST):

- For every node, all keys in its left subtree are smaller than the key value in that node.
- For every node, all keys in its right subtree are greater than the key value in that node.
- All nodes should have keys that is "unique"

Pre-order: ROOT -> LEFT -> RIGHT
In-order: LEFT -> ROOT -> RIGHT
Post-order: LEFT -> RIGHT-> ROOT

## Implementation

```cpp
#include <iostream>
using namespace std;

class node{
    public:
        int data;
        node *left;
        node *right;
        node(int v){
            this->data = v;
            this->left = this->right = NULL;
        }
};

void inOrder(node* Node){
    if(Node == NULL){
        return;
    }
    
    inOrder(Node->left);
    
    cout << Node->data << " ";
    
    inOrder(Node->right);
}


void postOrder(node* Node){
    if(Node == NULL){
        return;
    }
    
    postOrder(Node->left);
    postOrder(Node->right);
    cout << Node->data << " ";
    
}

void preOrder(node* Node){
    if(Node == NULL){
        return;
    }
    
    cout << Node->data << " ";
    preOrder(Node->left);
    preOrder(Node->right);
}


int main()
{
    
    node* root = new node(8);
    root->left = new node(5);
    root->left->left = new node(9);
    root->left->right = new node(7);
    root->left->right->left = new node(1);
    root->left->right->right = new node(12);
    root->left->right->right->left = new node(2);
    root->right = new node(4);
    root->right->right = new node(11);
    root->right->right->left = new node(3);
    
    cout << "Inorder Traversal: ";
    inOrder(root);
    cout << endl;
    cout << "Postorder Traversal: ";
    postOrder(root);
    cout << endl;
    cout << "Preorder Traversal: ";
    preOrder(root);
    
    return