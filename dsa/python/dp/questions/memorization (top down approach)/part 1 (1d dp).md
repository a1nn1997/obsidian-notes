#  **Fibonacci Number**

^637873

```python
input (n: int)

arr = [0]*n+1
arr[i] = arr[i-1]+arr[i-2]
return arr[n]
```

#  **House Robber**

^8052c4

```python
input (nums: list)

arr = [0]*n
arr[0], arr[1] = nums[0], max(nums[0], nums[1])
arr[i] = max(arr[i-1],arr[i-2]+nums[i])
return arr[n-1]
```

# Min Cost of climbing stairs

```python
input (cost: list)
n = len(cost)
dp = [0]*(n+1)
for i in range(2,n+1):
	dp[i] = min(dp[i-1]+cost[i-1], dp[i-2]+cost[i-2)
return dp[n]
```

#  **Maximum Subarray**

```python
input (nums: list)

cs = ms = nums[0]
for i in nums[1:]:
	cs = max(i, cs+i)
	ms = max(ms,cs)
return ms
```


#  Can Partition

```python
input (nums: list)

total_sum = sum(nums)
if total_sum % 2 != 0:
	return False
target = total_sum // 2
dp = [False] * (target + 1)
dp[0] = True
for num in nums:
	for i in range(target, num - 1, -1):
		dp[i] = dp[i] or dp[i - num]
return dp[target]
```


# Longest Increasing Subsequence

```python
input(nums:list)

dp = []
for num in nums:
	i = self.binarySearch(dp, num)
	if i == len(dp):
		dp.append(num)
	else:
		dp[i] = num
return len(dp)

binarySearch(sub, val):
lo, hi = 0, len(sub)
while lo < hi:
	mid = (lo + hi) // 2
	if sub[mid] < val:
		lo = mid + 1
	else:
		hi = mid
return lo
```

# Word Break

```python
input( word_set: str, wordDict: list)

word_set = set(wordDict)
ls = len(s) +1
dp = [False] * ls
dp[0] = True
for i in range(1, ls):
	for j in range(i):
		if dp[j] and s[j:i] in word_set:
			dp[i] = True
	break
return dp[ls-1]
```