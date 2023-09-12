# permutation

^87cf7f

```python
from itertools import permutations
```

1. get all combinations of string

```python
from itertools import permutations
s = "abc"

ans = list(permutations(s))

for a in ans:
    print(''.join(a))
```


# combinations

^0e9fa7

2. combinations sum

```python
from itertools import combinations

a = [10,1,2,7,6,1,5]
b = 8
ans = []
for r in range(1, len(a) + 1):
    for l in combinations(a, r):
        if sum(l)==b:
            ans.append(l)
print(ans)

```

# combinations_with_replacement

^a4092f

2 combinations sum with repeatations

```python
from itertools import combinations_with_replacement

a = [10,1,2,7,6,1,5]
b = 8
ans = []
for r in range(1, len(a) + 1):
    for l in combinations_with_replacement(a, r):
        if sum(l)==b:
            ans.append(l)
print(ans)
```
