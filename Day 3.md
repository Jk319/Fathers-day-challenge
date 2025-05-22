
# Mother's and Father's Day Challenges – Day 3
LeetCode Profile -  [Jatin kushwaha](https://leetcode.com/u/Jatin_kushwaha/) <br>
> **Tags**: #java  #DrGvishwanathanChallenge #shriramsir

##  Day 3:
**Problem Description** - Longest Valid Parentheses

Solution
```java
class Solution {
    public int longestValidParentheses(String S) {
        int left=0;
        int right=0;
        int max=0;
        for(int i=0;i<S.length();i++)
        {
            if(S.charAt(i)=='(')
            {
                left++;
            }
            else
            {
                right++;
            }
            if(left==right)
            {
                max=Math.max(max,left*2);
            }
            else if(right>left)
            {
                left=0;
                right=0;
            }
        }
        left=0;
        right=0;
        for(int i=S.length()-1;i>=0;i--)
        {
             if(S.charAt(i)=='(')
             {
                left++;
            }
            else
            {
                right++;
            }
            if(left==right)
            {
                max=Math.max(max,left*2);
            }
            else if(left>right)
            {
                left=0;
                right=0;
            }
        }
        return max;
    }
}
```

---

**Problem Description** - Search Insert Position

Solution 
```java
class Solution {
    public int searchInsert(int[] nums, int target) {
        int start = 0;
        int end = nums.length-1;

        while (start <= end) {
            int mid = start + (end-start)/2;
            if (nums[mid] == target) return mid;
            else if (nums[mid] > target) end = mid-1;
            else start = mid+1;
        }

        return start;
    }
}
```
