Problem:
<br>
[Rotating the Box](https://leetcode.com/problems/rotating-the-box/description/?envType=daily-question&envId=2024-11-23)
<br>
Solution:
<br>
class Solution {
    public char[][] rotateTheBox(char[][] box) {
        int n=box.length;
        int m=box[0].length;
        char charrot[][]=new char[m][n];
        for(int i=n-1;i>=0;i--)
        {
            for(int j=0;j<m;j++)
            {
                charrot[j][n-i-1]=box[i][j];
            }
        }
        for(int i=0;i<n;i++)
        {
            int k=-1;
            for(int j=0;j<m;j++)
            {
                if(charrot[j][i]=='#'&&k==-1)
                k=j;
                if(charrot[j][i]=='.'&&k!=-1)
                {
                    char temp=charrot[j][i];
                    charrot[j][i]=charrot[k][i];
                    charrot[k][i]=temp;
                    k=k+1;
                }
                if(charrot[j][i]=='*')
                k=-1;
            }
        }
        return charrot;
    }
}