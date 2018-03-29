# DP
## 动态规划的递推写法（自底向上）
记忆化搜索  
***
1 数塔问题   

状态转移方程：dp[i][j] = max(dp[i+1][j],dp[i+1][j+1])+f[i][j]  

边界： dp[n][j] = f[n][j]  
***
2 最大连续自序列和 O(n) 

令状态dp[i]表示以A[i]作为末尾的连续序列的最大和  

状态转移方程：dp[i] = max(A[i],dp[i-1]+A[i])  

边界：dp[0] = A[0]  
***
3 最长不下降自序列(LIS)  

状态转移方程：dp[i] = max{1,dp[j]+1}（j=1,2,...,i-1 && A[j]<A[i])  

其中隐含的边界：dp[i] = 1.   

重复计算：每次碰到子问题“A[i]结尾的最长不下降自序列“时，都去重新遍历所有子序列。  
***
4 最长公共子序列（LCS） 

状态转移方程： dp[i][j] = dp[i-1][j-1]+1,A[i]==B[j] ; max{dp[i-1][j],dp[i][j-1]},A[i]!=B[j]  

边界：dp[i][0] = dp[0][j] = 0 (0<=i<=n,0<=j<=m). 
***
5 最长回文子串  

考虑按子串的长度和子串的初始位置进行枚举  

先枚举子串长度L，再枚举左端点i，可以得到右端点i+L-1。



