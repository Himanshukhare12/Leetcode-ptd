Problem:
<br>
[Circular Sentence](https://leetcode.com/problems/circular-sentence/description/?envType=daily-question&envId=2024-11-02)
<br>
Solution:
<br>

class Solution {
    public boolean isCircularSentence(String sentence) {
        int n=sentence.length();
        for(int i=0;i<n;i++)
        {
            if(sentence.charAt(i)==' ')
            {
                if(sentence.charAt(i-1)!=sentence.charAt(i+1))
                return false;
            }
            if(i==n-1&&sentence.charAt(i)==sentence.charAt(0))
            {
               return true;
            }
        }
        return false;
    }
}
