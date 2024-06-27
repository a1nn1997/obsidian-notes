#  Coin Change 1

```python
input(coins: list, amount: int)
dp = [float(inf)]*(amount+1)
dp[0] = 0
for coin in coins:
	for x in range(coins, amount+1):
		dp[x] = min(dp[x], dp[x-coin]+1)
return dp[amount] if dp[amount] != float('inf') else -1
```

# Longest Palindromic Subsequence

```python
input(s: str)
n = len(s)
dp = [[0] * n for _ in range(n)]
for i in range(n - 1, -1, -1):
	dp[i][i] = 1
	for j in range(i + 1, n):
	if s[i] == s[j]:
		dp[i][j] = dp[i + 1][j - 1] + 2
	else:
		dp[i][j] = max(dp[i + 1][j], dp[i][j - 1])
return dp[0][n - 1]
```

# Longest common subsequence

```python
input( text1: str, text2: str)

m, n = len(text1), len(text2)
dp = [[0] * (n + 1) for _ in range(m + 1)]
for i in range(1, m + 1):
	for j in range(1, n + 1):
		if text1[i - 1] == text2[j - 1]:
			dp[i][j] = dp[i - 1][j - 1] + 1
		else:
			dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])
return dp[m][n]
```