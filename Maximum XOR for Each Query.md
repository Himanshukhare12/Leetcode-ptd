Problem:
<br>
[Maximum XOR for Each Query](https://leetcode.com/problems/maximum-xor-for-each-query/description/?envType=daily-question&envId=2024-11-08)
<br>
Solution:
<br>
class Solution {
    public int[] getMaximumXor(int[] nums, int maximumBit) {
     int n=nums.length;
     int arr[]=new int[n];
     int arr2[]=new int[n];
     int c=0;
     arr[0]=nums[0];
     
     for(int i=1;i<n;i++)
     {
        arr[i]=arr[i-1]^nums[i];
     }
         for(int j=n-1;j>=0;j--)
    {
        int ansr=0;
        int max=(1<<maximumBit)-1;
        arr2[c++]=arr[j]^max;
          
    } 
          return arr2;
    }
}