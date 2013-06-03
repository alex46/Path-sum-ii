Path-sum-ii
===========

Path sum ii
/**
 * Definition for binary tree
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
public class Solution {
    public ArrayList<ArrayList<Integer>> pathSum(TreeNode root, int sum) {
        // Start typing your Java solution below
        // DO NOT write main() function
         ArrayList<ArrayList<Integer>> reSet = new ArrayList<ArrayList<Integer>>();
         findPathSum(root,sum,reSet);
         return reSet;
    }
    
    public void findPathSum(TreeNode root, int sum, ArrayList<ArrayList<Integer>> reSet){
         
        if(root == null) return;
        
       
         
        while(root!=null){
        ArrayList result = new ArrayList();
       
        int partSum = sum - root.val;
        result.add(root.val);
        
        if(partSum==0 && root.left == null & root.right == null){
        reSet.add(result);

        }
        
    
        else{
        if(root.left!=null)
        findPathSum(root.left,partSum,reSet);
        
        if(root.right!=null)
        findPathSum(root.right,partSum,reSet);
        
        }
        
    }
    
}
}
