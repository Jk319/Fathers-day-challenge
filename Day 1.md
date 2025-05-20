
# Mother's and Father's Day Challenges – Day 1
LeetCode Profile -  [Jatin kushwaha](https://leetcode.com/u/Jatin_kushwaha/) <br>
> **Tags**: #java #50daysofcode #DrGvishwanathanChallenge #shriramsir

##  Day 1:
**Problem Description** - Valid Parenthesis String

Solution
```java
class Solution {
    public boolean checkValidString(String s) {
        int n = s.length();
        boolean[][] dp = new boolean[n][n];
        for (int i = 0; i < n; ++i) {
            dp[i][i] = s.charAt(i) == '*';
        }
        for (int i = n - 2; i >= 0; --i) {
            for (int j = i + 1; j < n; ++j) {
                char a = s.charAt(i), b = s.charAt(j);
                dp[i][j] = (a == '(' || a == '*') && (b == '*' || b == ')')
                    && (i + 1 == j || dp[i + 1][j - 1]);
                for (int k = i; k < j && !dp[i][j]; ++k) {
                    dp[i][j] = dp[i][k] && dp[k + 1][j];
                }
            }
        }
        return dp[0][n - 1];
    }
}
```

---

**Problem Description** - Pascal's Triangle II

Solution - 
```java
public class Solution {
    public List<Integer> getRow(int rowIndex) {
        List<Integer> res = new ArrayList<>();
        if( rowIndex < 0 ) return res;
        
        for( int i = 0; i <= rowIndex; i++ ){
            res.add( 0, 1 );
            for( int j = 1; j < res.size() - 1; j++ ){
                res.set( j , res.get(j) + res.get(j+1) );
            }
        }
        return res;
    }
}
```
