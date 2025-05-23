
# Mother's and Father's Day Challenges – Day 4
LeetCode Profile -  [Jatin kushwaha](https://leetcode.com/u/Jatin_kushwaha/) <br>
> **Tags**: #java  #DrGvishwanathanChallenge #shriramsir

##  Day 4:
**Problem Description** - Move Zeroes

Solution
```java
class Solution {
    public void moveZeroes(int[] nums) {
        int j = 0;
       // int arr[] = new int [nums.length];
        for(int i =0;i<nums.length;i++){
            if(nums[i]!=0){
               nums[j]=nums[i];
               j++;
            }
        }
        while(j<nums.length){
            nums[j]=0;
            j++;
        }
      
    
}
```

---

**Problem Description** -  Basic Calculator

Solution 
```java
class Solution {
    int idx; 
    public int calculate(String s) {
        idx = 0; 
        return calc(s);
    }
    
    private int calc(String s) {
        int res = 0, num = 0, sign = 1;
        while (idx < s.length()) {
            char c = s.charAt(idx++);
            if (c >= '0' && c <= '9') num = num * 10 + c - '0';
            else if (c == '(') num = calc(s); 
            else if (c == ')') return res + sign * num;
            else if (c == '+' || c == '-') { 
                res += sign * num;
                num = 0;
                sign = c == '-' ? -1 : 1;
            }
        }
        return res + sign * num; 
    }
}
```
