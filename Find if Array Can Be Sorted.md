Problem:
<br>
[Find if Array Can Be Sorted](https://leetcode.com/problems/find-if-array-can-be-sorted/description/?envType=daily-question&envId=2024-11-06)
<br>
Solution:
<br>
class Solution {
    public boolean canSortArray(int[] nums) {
        int setbit=Integer.bitCount(nums[0]);
        int max=nums[0];
        int min=nums[0];
        int maxprev=Integer.MIN_VALUE;
        for(int i=1;i<nums.length;i++)
        {
            if(Integer.bitCount(nums[i])==setbit)
            {
                max=Math.max(max,nums[i]);
                min=Math.min(min,nums[i]);
            }
            else
            {
                if(maxprev>min)
                return false;
                maxprev=max;
                max=nums[i];
                min=nums[i];
                setbit=Integer.bitCount(nums[i]);
            }
        }
       if(maxprev>min)
       return false;
       return true;
    }
}