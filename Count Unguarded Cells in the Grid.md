Problem:
<br>
[Count Unguarded Cells in the Grid](https://leetcode.com/problems/count-unguarded-cells-in-the-grid/description/)
<br>
Solution:
<br>
class Solution {

    int UNGUARDED = 0;
    int GUARDED = 1;
    int GUARD = 2;
    int WALL = 3;

    public void markguarded(int row, int col, int[][] grid) {
        for (int r = row - 1; r >= 0; r--) {
            if (grid[r][col] == WALL || grid[r][col] == GUARD) break;
            grid[r][col] = GUARDED;
        }
        for (int r = row + 1; r < grid.length; r++) {
            if (grid[r][col] == WALL || grid[r][col] == GUARD) break;
            grid[r][col] = GUARDED;
        }
        for (int c = col - 1; c >= 0; c--) {
            if (grid[row][c] == WALL || grid[row][c] == GUARD) break;
            grid[row][c] = GUARDED;
        }
        for (int c = col + 1; c < grid[0].length; c++) {
            if (grid[row][c] == WALL || grid[row][c] == GUARD) break;
            grid[row][c] = GUARDED;
        }
    }

    public int countUnguarded(int m, int n, int[][] guards, int[][] walls) {
        int[][] grid = new int[m][n];

        // Mark guards' positions
        for (int[] guard : guards) {
            grid[guard[0]][guard[1]] = GUARD;
        }
        for (int[] wall : walls) {
            grid[wall[0]][wall[1]] = WALL;
        }

        for (int[] guard : guards) {
            markguarded(guard[0], guard[1], grid);
        }
        int count = 0;
        for (int[] row : grid) {
            for (int cell : row) {
                if (cell == UNGUARDED) count++;
            }
        }
        return count;
    }
}