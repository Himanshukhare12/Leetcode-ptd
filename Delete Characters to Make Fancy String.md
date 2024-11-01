Problem:[Delete Characters to Make Fancy String]([https://leetcode.com/problems/two-sum/](https://leetcode.com/problems/delete-characters-to-make-fancy-string/description/))
Solution:
class Solution {
    public String makeFancyString(String s) {
        StringBuilder st=new StringBuilder();
        int c=0;
       for(int i=0;i<s.length()-1;i++)
       {
        if(s.charAt(i)==s.charAt(i+1))
        {
            c++;
        }
        else
        {
            c=0;
        }
        if(c<2)
        {
            st.append(s.charAt(i));
        }}
        st.append(s.charAt(s.length()-1));
       return st.toString();
    }
}
