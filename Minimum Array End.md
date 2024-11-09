Problem:
<br>
[Minimum Array End](https://leetcode.com/problems/minimum-array-end/)
<br>
Solution:
<br>

class Solution {
    public long minEnd(int n, int x) {
        long ansr=x;
        while(--n>0)
        {
            ansr=(ansr+1)|x;
        }
        return ansr;
    }
}