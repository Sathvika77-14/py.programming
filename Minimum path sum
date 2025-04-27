class Solution(object):
    def minPathSum1(self, grid):
        r, c = len(grid), len(grid[0])
        dp = [[grid[0][0] for _ in range(c)] for _ in range(r)]
        for i in range(1, r):
            dp[i][0] = dp[i-1][0] + grid[i][0]
        for j in range(1, c):
            dp[0][j] = dp[0][j-1] + grid[0][j]
        for i in range(1, r):
            for j in range(1, c):
                dp[i][j] = min(dp[i-1][j], dp[i][j-1]) + grid[i][j]
        return dp[-1][-1]
    
    def minPathSum(self, grid):
        r, c = len(grid), len(grid[0])
        dp = [grid[0][0] for _ in range(c)]
        for j in range(1, c):
            dp[j] = dp[j-1] + grid[0][j]
        for i in range(1, r):
            dp[0] += grid[i][0]
            for j in range(1, c):
                dp[j] = min(dp[j-1], dp[j]) + grid[i][j]
        return dp[-1]
