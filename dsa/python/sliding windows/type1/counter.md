# 1. Longest Substring with At Most K Distinct Characters

```python3
if len(s) == 0 or k > len(s):
	return 0
c = Counter(s)
sub1, sub2 = "", ""
for i, letter in enumerate(s):
	if c[letter] < k:
		sub1 = self.longestSubstring(s[:i], k)
		sub2 = self.longestSubstring(s[i+1:], k)
		break
	else:
		return len(s)
return max(sub1, sub2)
```


# 2. **Permutation in String**

```python
from collections import Counter
len_s1, len_s2 = len(s1), len(s2)
if len_s1 > len_s2:
	return False
s1_count = Counter(s1)
window_count = Counter(s2[:len_s1])
if s1_count == window_count:
	return True
for i in range(len_s1, len_s2):
	window_count[s2[i]] += 1
	window_count[s2[i - len_s1]] -= 1
	if window_count[s2[i - len_s1]] == 0:
		del window_count[s2[i - len_s1]]
	if s1_count == window_count:
		return True
return False
```

#  3. **Find All Anagrams in a String**

```python
len_p, len_s = len(p), len(s)
if len_p > len_s:
	return []
p_count = Counter(p)
window_count = Counter(s[:len_p])
result = []
if p_count == window_count:
	result.append(0)
for i in range(len_p, len_s):
	window_count[s[i]] += 1
	window_count[s[i - len_p]] -= 1
	if window_count[s[i - len_p]] == 0:
		del window_count[s[i - len_p]]
	if p_count == window_count:
		result.append(i - len_p + 1)
return result
```
