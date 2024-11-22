Problem:
<br>
[Flip Columns For Maximum Number of Equal Rows](https://leetcode.com/problems/flip-columns-for-maximum-number-of-equal-rows/description/)
Solution:
<br>
class Solution {
    public int maxEqualRowsAfterFlips(int[][] matrix) {
        HashMap<String,Integer>hm=new HashMap<>();
        for(int row[]:matrix)
        {
            StringBuilder sb=new StringBuilder();
            for(int i=0;i<row.length;i++)
            {
                if(row[0]==row[i])
                sb.append("T");
                else
                sb.append("F");
            }
            String S=sb.toString();
            hm.put(S,hm.getOrDefault(S,0)+1);
        }
        int maxfreq=0;
        for(int a:hm.values())
        {
            maxfreq=Math.max(maxfreq,a);
        }
        return maxfreq;
        }
    }

