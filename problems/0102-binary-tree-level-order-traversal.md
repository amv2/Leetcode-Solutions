Java Solution
```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
    public List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> res = new LinkedList<>();
        if (root == null) return res;

        Queue<TreeNode> q = new LinkedList<>();
        q.add(root);

        while (!q.isEmpty()) {
            int len = q.size();
            LinkedList<Integer> level = new LinkedList<>();
            
            for (int i=0; i<len; i++) {
                TreeNode n = q.poll();
                if (n.right != null) q.add(n.right);
                if (n.left != null) q.add(n.left);
                level.push(n.val);
            }
            res.add(level);
        }
        return res;
    }
}
```