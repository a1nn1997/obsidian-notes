# **Best Time to Buy and Sell Stock**

```python
input: prices [int]
min_price = float('inf')
max_profit = 0
        
for price in prices:
    min_price = min(min_price, price)
    max_profit = max(max_profit, price - min_price)
        
return max_profit
```

# House Robber ||

```python
input nums : [int]

if len(nums) == 1:
	return nums[0]
def rob_linear(nums):
	prev2, prev1 = 0, 0
	for num in nums:
		curr = max(prev1, prev2 + num)
		prev2 = prev1
		prev1 = curr
	return curr
return max(rob_linear(nums[:-1]), rob_linear(nums[1:]))
```

