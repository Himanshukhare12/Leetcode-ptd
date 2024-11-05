Problem:
<br>
[Minimum Number of Changes to Make Binary String Beautiful](https://leetcode.com/problems/minimum-number-of-changes-to-make-binary-string-beautiful/description/)
<br>
Solution:
<br>
class Solution {
    public int minChanges(String s) {
        int change=0;
        for(int i=0;i<s.length();i+=2)
        {
            if(s.charAt(i)!=s.charAt(i+1))
            change++;
        }
        return change;
    }
}