Problem:
<br>
[Shortest Subarray With OR at Least K II](https://leetcode.com/problems/shortest-subarray-with-or-at-least-k-ii/description/)
<br>
Solution:
<br>
class Solution {

    public int minimumSubarrayLength(int[] nums, int k) {
        int minLength = Integer.MAX_VALUE;
        int Start = 0;
        int End = 0;
        int[] bitCounts = new int[32];
        while (End < nums.length) {
            updateBitCounts(bitCounts, nums[End], 1);
            while (
                Start <= End &&
                convertBitCountsToNumber(bitCounts) >= k
            ) {
                minLength = Math.min(minLength,End -Start + 1);
                updateBitCounts(bitCounts, nums[Start], -1);
                Start++;
            }

            End++;
        }

        return minLength == Integer.MAX_VALUE ? -1 : minLength;
    }
    public void updateBitCounts(int[] bitCounts, int number, int delta) {
        for (int bitPosition = 0; bitPosition < 32; bitPosition++) {
            if (((number >> bitPosition) & 1) != 0) {
                bitCounts[bitPosition] += delta;
            }
        }
    }
    public int convertBitCountsToNumber(int[] bitCounts) {
        int result = 0;
        for (int bitPosition = 0; bitPosition < 32; bitPosition++) {
            if (bitCounts[bitPosition] != 0) {
                result |= 1 << bitPosition;
            }
        }
        return result;
    }
}