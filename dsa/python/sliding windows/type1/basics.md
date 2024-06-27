# 1. **Longest Substring Without Repeating Characters**

```python
char_index_map = {}
left = 0
max_length = 0

for right, char in enumerate(s):
	if char in char_index_map and char_index_map[char] >= left:
		left = char_index_map[char] + 1
	char_index_map[char] = right
	max_length = max(max_length, right - left + 1)
return max_length
```

# 2.  **Longest Repeating Character Replacement** 

```python
from collections import defaultdict
count = defaultdict(int)
max_count = 0
left = 0
result = 0
for right in range(len(s)):
	count[s[right]] += 1
	max_count = max(max_count, count[s[right]])
	if (right - left + 1) - max_count > k:
		count[s[left]] -= 1
	left += 1
	result = max(result, right - left + 1)
return result
```


# 3. **Max Consecutive Ones III**

```python
left = 0
max_length = 0
zero_count = 0
for right in range(len(nums)):
	if nums[right] == 0:
		zero_count += 1
	while zero_count > k:
		if nums[left] == 0:
			zero_count -= 1
		left += 1
	max_length = max(max_length, right - left + 1)
return max_length
```

# 4. Fruit Into Baskets

```python
from collections import defaultdict
basket = defaultdict(int)
left = 0
max_fruits = 0
for right in range(len(fruits)):
	basket[fruits[right]] += 1
	while len(basket) > 2:
		basket[fruits[left]] -= 1
		if basket[fruits[left]] == 0:
			del basket[fruits[left]]
		left += 1
	max_fruits = max(max_fruits, right - left + 1)
return max_fruits
```

# 5. Maximum Sum of Two Non-Overlapping Subarrays

```python
def get_prefix_sums(nums):
	prefix_sums = [0] * (len(nums) + 1)
	for i in range(1, len(prefix_sums)):
		prefix_sums[i] = prefix_sums[i - 1] + nums[i - 1]
return prefix_sums

prefix_sums = get_prefix_sums(nums)
max_sum = 0
max_first_before_second = 0
for i in range(firstLen + secondLen, len(nums) + 1):
	max_first_before_second = max(max_first_before_second, prefix_sums[i - secondLen] - prefix_sums[i - secondLen - firstLen])
	max_sum = max(max_sum, max_first_before_second + prefix_sums[i] - prefix_sums[i - secondLen])

max_second_before_first = 0

for i in range(firstLen + secondLen, len(nums) + 1):
	max_second_before_first = max(max_second_before_first, prefix_sums[i - firstLen] - prefix_sums[i - firstLen - secondLen])
	max_sum = max(max_sum, max_second_before_first + prefix_sums[i] - prefix_sums[i - firstLen])
return max_sum
```

# 6.  Count Number of Nice Subarrays

```python
from collections import defaultdict
count = 0
prefix_sum = 0
prefix_counts = defaultdict(int)
prefix_counts[0] = 1
for num in nums:
	if num % 2 == 1:
		prefix_sum += 1
	if prefix_sum - k in prefix_counts:
		count += prefix_counts[prefix_sum - k]
	prefix_counts[prefix_sum] += 1
return count
```


# 7. Grumpy Bookstore Owner

```python
n = len(customers)
always_satisfied = sum(customers[i] for i in range(n) if grumpy[i] == 0)
additional_satisfied = 0
for i in range(minutes):
	if grumpy[i] == 1:
		additional_satisfied += customers[i]
max_additional_satisfied = additional_satisfied
for i in range(minutes, n):
	if grumpy[i] == 1:
		additional_satisfied += customers[i]
	if grumpy[i - minutes] == 1:
		additional_satisfied -= customers[i - minutes]
	max_additional_satisfied = max(max_additional_satisfied, additional_satisfied)
return always_satisfied + max_additional_satisfied
```

# 8. Maximum Points You Can Obtain from Cards

```python
n = len(cardPoints)
total_sum = sum(cardPoints)
if k == n:
	return total_sum
window_sum = sum(cardPoints[:n - k])
min_window_sum = window_sum
for i in range(n - k, n):
	window_sum += cardPoints[i] - cardPoints[i - (n - k)]
	min_window_sum = min(min_window_sum, window_sum)
return total_sum - min_window_sum
```

# 9. Subarray Product Less Than K

```python
if k <= 1:
    return 0
prod = 1
left = 0
count = 0
for right in range(len(nums)):
	prod *= nums[right]
	while prod >= k and left <= right:
		prod /= nums[left]
		left += 1
	count += right - left + 1
return count
```

# 10 **K-Diff Pairs in an Array**

```python
if k < 0:
	return 0
count = 0
freq = {}
for num in nums:
	if num in freq:
		freq[num] += 1
	else:
		freq[num] = 1
if k == 0:
	for key in freq:
		if freq[key] > 1:
			count += 1
else:
	for key in freq:
		if key + k in freq:
			count += 1
return count
```