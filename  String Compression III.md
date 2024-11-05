Problem:
<br>
[ String Compression III](https://leetcode.com/problems/string-compression-iii/description/?envType=daily-question&envId=2024-11-04)
<br>
Solution:
<br>
class Solution {
    public String compressedString(String word) {
        StringBuilder comp=new StringBuilder();
        int i=0;
        while(i<word.length())
        {
            char currentch=word.charAt(i);
            int count=0;
              while(i<word.length()&&currentch==word.charAt(i)&&count<9)
              {
                i++;
                count++;
              }
              comp=comp.append(Integer.toString(count)+currentch);
        }
        return comp.toString();
    }
}