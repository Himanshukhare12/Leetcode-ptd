Problem:
<br>
[Largest Combination With Bitwise AND Greater Than Zero](https://leetcode.com/problems/largest-combination-with-bitwise-and-greater-than-zero/description/?envType=daily-question&envId=2024-11-07)
<br>
Solution:
<br>
class Solution {
    public int largestCombination(int[] candidates) {
        int n=candidates.length;
        int max=Integer.MIN_VALUE;
          for(int i=0;i<24;i++)
          {
            int count=0;
            for(int j=0;j<n;j++)
            {
                if((candidates[j]&(1<<i))!=0)
                count++;
            }
          max=Math.max(max,count);
        }
        return max;
    }
}