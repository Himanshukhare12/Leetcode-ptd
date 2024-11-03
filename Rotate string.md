Problem:
<br>
[Rotate String](https://leetcode.com/problems/rotate-string/description/)
<br>
Solution:
<br>
class Solution {
    public boolean rotateString(String s, String goal) {
         if (s.length() != goal.length()) {
            return false;
          } 
          String st=s+s;
          return st.contains(goal);
        
    }
}