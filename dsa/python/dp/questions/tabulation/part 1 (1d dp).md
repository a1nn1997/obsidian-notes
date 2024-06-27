# Climbing Stairs
```python
input = n: int

dp = [1]*n
dp[0] = 1
dp[1] = 2
for i in range(2,n):
	dp[i] = dp[i-1]+dp[i-2]
return dp[n-1]
```

# find target sum ways

```python
input nums: [int], target: int

total_sum = sum(nums)
if (total_sum + target) % 2 != 0 or abs(target) > total_sum:
	return 0
subset_sum = (total_sum + target) // 2
dp = [0] * (subset_sum + 1)
dp[0] = 1
for num in nums:
	for j in range(subset_sum, num - 1, -1):
		dp[j] += dp[j - num]
return dp[subset_sum]
```

# decode ways

```python
input s: str

if not s or s[0] == '0':
	return 0
n = len(s)
dp = [0] * (n + 1)
dp[0] = 1  # There's one way to decode an empty string
dp[1] = 1  # There's one way to decode a string if it doesn't start with '0'
for i in range(2, n + 1):
	if s[i - 1] != '0':
		dp[i] += dp[i - 1]
	two_digit = int(s[i - 2:i])
	if 10 <= two_digit <= 26:
		dp[i] += dp[i - 2]
return dp[n]
```

# Number of Longest Increasing Subsequence

```python
input nums: [int]

if not nums:
	return 0
n = len(nums)
lengths = [1] * n
counts = [1] * n
for i in range(n):
	for j in range(i):
		if nums[i] > nums[j]:
			if lengths[j] + 1 > lengths[i]:
				lengths[i] = lengths[j] + 1
				counts[i] = counts[j]
			elif lengths[j] + 1 == lengths[i]:
				counts[i] += counts[j]
				longest = max(lengths)
total_count = sum(count for length, count in zip(lengths, counts) if length == longest)
return total_count
```