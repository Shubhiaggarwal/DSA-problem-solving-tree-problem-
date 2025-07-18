# DSA-problem-solving-tree-problem-
tree level question (easy to medium)

class Solution {
public:
    vector<vector<int>> levelOrder(TreeNode* root) {
    vector<vector<int>> result;    
    if(root == nullptr){
        return result;
    }
    queue<TreeNode*> queue;
    queue.push(root);
    while(!queue.empty()){
        int levelsize = queue.size();
        vector<int> currentlevel;
        for(int i=0;i<levelsize;i++){
            TreeNode* currentnode = queue.front();
            queue.pop();
            currentlevel.push_back(currentnode->val);
            if(currentnode->left!=nullptr){
                queue.push(currentnode->left);
            }
            if(currentnode->right!=nullptr){
                queue.push(currentnode->right);
            }
        }
        result.push_back(currentlevel);
    }
          return result;
    }
};
