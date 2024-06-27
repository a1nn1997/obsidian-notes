# **Unique Paths**

```python
input (m, n int, int)
dp = [[0] * n for _ in range(m)]
for i in range(m):
	dp[i][0] = 1
for j in range(n):
	dp[0][j] = 1
for i in range(1, m):
	for j in range(1, n):
		dp[i][j] = dp[i-1][j] + dp[i][j-1]
return dp[m-1][n-1]
```

# Edit Distance

```python
m, n = len(word1), len(word2)
dp = [[0] * (n + 1) for _ in range(m + 1)]
for i in range(m + 1):
    dp[i][0] = i  # Deleting all characters of word1 to match an empty word2
for j in range(n + 1):
    dp[0][j] = j  # Inserting all characters of word2 to match an empty word1
for i in range(1, m + 1):
    for j in range(1, n + 1):
        if word1[i - 1] == word2[j - 1]:
            dp[i][j] = dp[i - 1][j - 1]  # No operation needed if characters match
        else:
            dp[i][j] = min(
                dp[i - 1][j] + 1,    # Deletion
                dp[i][j - 1] + 1,    # Insertion
                dp[i - 1][j - 1] + 1 # Replacement
            )
return dp[m][n]
```

# Min Path Sum

```python
input grid : [[int]]

m, n = len(grid), len(grid[0])
dp = [[0] * n for _ in range(m)]
dp[0][0] = grid[0][0]
for j in range(1, n):
	dp[0][j] = dp[0][j - 1] + grid[0][j]
for i in range(1, m):
	dp[i][0] = dp[i - 1][0] + grid[i][0]
for i in range(1, m):
	for j in range(1, n):
		dp[i][j] = min(dp[i - 1][j], dp[i][j - 1]) + grid[i][j]
return dp[m - 1][n - 1]
```

# Knight Dialer

```python
input n: int

MOD = 10**9 + 7
moves = {
	0: [4, 6],
	1: [6, 8],
	2: [7, 9],
	3: [4, 8],
	4: [0, 3, 9],
	5: [],
	6: [0, 1, 7],
	7: [2, 6],
	8: [1, 3],
	9: [2, 4]
}
dp = [[0] * 10 for _ in range(n + 1)]
for digit in range(10):
	dp[1][digit] = 1

for i in range(2, n + 1):
	for digit in range(10):
		dp[i][digit] = sum(dp[i - 1][prev] for prev in moves[digit]) % MOD
return sum(dp[n]) % MOD
```

# Maximal Square

```python
input matrix [[0,1]] 0 1 matrix

if not matrix or not matrix[0]:
	return 0
m, n = len(matrix), len(matrix[0])
dp = [[0] * n for _ in range(m)]
max_side = 0
for i in range(m):
	for j in range(n):
		if matrix[i][j] == '1':
			if i == 0 or j == 0:
				dp[i][j] = 1
			else:
				dp[i][j] = min(dp[i-1][j], dp[i][j-1], dp[i-1][j-1]) + 1
			max_side = max(max_side, dp[i][j])
return max_side * max_side
```