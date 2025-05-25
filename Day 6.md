

# Mother's and Father's Day Challenges – Day 6
LeetCode Profile -  [Jatin kushwaha](https://leetcode.com/u/Jatin_kushwaha/) <br>
> **Tags**: #java  #DrGvishwanathanChallenge #shriramsir

##  Day 6:
**Problem Description** -Binary Tree Inorder Traversal

Solution
```java
class Solution {
    private List<Integer> res = new ArrayList<>();
    public List<Integer> inorderTraversal(TreeNode root) {
        traverse(root);
        return res;
    }
    
    private void traverse(TreeNode root) {
        if (root == null) {
            return;
        }
        traverse(root.left);
        res.add(root.val);
        traverse(root.right);
    }
}
```

---

**Problem Description** -  Find First and Last Position of Element in Sorted Array

Solution 
```java
class Solution {
    public int binarySearch(int[] nums, int target, boolean findFirst) {
        int s = 0;
        int e = nums.length - 1;
        int index = -1;
        while (s <= e) {
            int mid = s + (e - s) / 2;
            if (nums[mid] == target) {
                index = mid;
                if (findFirst)
                    e = mid - 1; // Find first occurrence
                else
                    s = mid + 1; // Find last occurrence
            } else if (nums[mid] < target)
                s = mid + 1;
            else
                e = mid - 1;
        }
        return index;
    }

    public int[] searchRange(int[] nums, int target) {
        int[] range = new int[2];
        int first = binarySearch(nums, target, true);
        int last = binarySearch(nums, target, false);
        range[0] = first;
        range[1] = last;
        return range;
    }
}



```
