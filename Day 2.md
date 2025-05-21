
# Mother's and Father's Day Challenges – Day 2
LeetCode Profile -  [Jatin kushwaha](https://leetcode.com/u/Jatin_kushwaha/) <br>
> **Tags**: #java  #DrGvishwanathanChallenge #shriramsir

##  Day 2:
**Problem Description** - Majority Element

Solution
```java
class Solution {
  public int majorityElement(int[] nums) {
    Integer ans = null;
    int count = 0;

    for (final int num : nums) {
      if (count == 0)
        ans = num;
      count += num == ans ? 1 : -1;
    }

    return ans;
  }
}

```

---

**Problem Description** - Minimum Remove to Make Valid Parentheses

Solution 
```java
class Solution {
    public String minRemoveToMakeValid(String s) {
        StringBuilder sb = new StringBuilder(s);
        Stack<Integer> open = new Stack<>();
        Stack<Integer> close = new Stack<>();

        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);

            if (c == '(') {
                open.push(i);
            } else if (c == ')') {
                if (open.isEmpty()) {
                    close.push(i);
                } else {
                    open.pop();
                }
            }
        }

        while (!open.isEmpty()) {
            sb.deleteCharAt(open.pop());
        }

        while (!close.isEmpty()) {
            sb.deleteCharAt(close.pop());
        }

        return sb.toString();
    }
}
```
