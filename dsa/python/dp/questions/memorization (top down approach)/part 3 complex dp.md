# Stone Game 2

```python
input( piles: list )
n = len(piles)
suffix_sum = [0] * (n + 1)
memo = {}
for i in range(n - 1, -1, -1):
	suffix_sum[i] = suffix_sum[i + 1] + piles[i]
def dp(index, M):
	if index >= n:
		return 0
	if 2 * M >= n - index:
		return suffix_sum[index]
	if (index, M) in memo:
		return memo[(index, M)]
	max_stones = 0
	for x in range(1, 2 * M + 1):
		if index + x > n:
			break
		next_gain = suffix_sum[index] - dp(index + x, max(M, x))
		max_stones = max(max_stones, next_gain)
	memo[(index, M)] = max_stones
	return max_stones
return dp(0, 1)
```