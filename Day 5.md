
# Mother's and Father's Day Challenges – Day 5
LeetCode Profile -  [Jatin kushwaha](https://leetcode.com/u/Jatin_kushwaha/) <br>
> **Tags**: #java  #DrGvishwanathanChallenge #shriramsir

##  Day 5:
**Problem Description** - Rotate Array

Solution
```java
class Solution {
    public static void reverse(int [] arr, int start, int end){
        while(start<end){
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;
            start++;
            end--;
        }
    }
    public void rotate(int[] nums, int k) {
        int n = nums.length;
        k = k%n;
        reverse(nums, 0, n-1-k);
        reverse(nums, n-k, n-1);
        reverse(nums, 0, n-1);
    }
}
```

---

**Problem Description** -  Implement Stack using Queues

Solution 
```java

class MyStack {
    Queue<Integer> q = new LinkedList<>();

    public MyStack() {

    }

    public void push(int x) {
        q.add(x);
    }

    public int pop() {
        for (int i = 1; i < q.size(); ++i) {
            q.add(q.remove());
        }
        return q.remove();
    }

    public int top() {
        for (int i = 1; i < q.size(); ++i) {
            q.add(q.remove());
        }
        int x = q.remove();
        q.add(x);
        return x;
    }

    public boolean empty() {
        if (q.size() > 0)
            return false;
        return true;
    }
}


```
