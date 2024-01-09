void find_Leaf_dfs(TreeNode* nodeNow, vector<int>& nodeList) {
        if (!nodeNow) {
            return;
        }

        if (!nodeNow->left && !nodeNow->right) {
            nodeList.push_back(nodeNow->val);
            return;
        }

        find_Leaf_dfs(nodeNow->left, nodeList);
        find_Leaf_dfs(nodeNow->right, nodeList);
    }
    bool leafSimilar(TreeNode* root1, TreeNode* root2) {
        vector<int> nodeList_root1, nodeList_root2;
        find_Leaf_dfs(root1, nodeList_root1);
        find_Leaf_dfs(root2, nodeList_root2);
        return nodeList_root1 == nodeList_root2;
    }
