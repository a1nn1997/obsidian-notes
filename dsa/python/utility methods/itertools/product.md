
# product

^b5f504

```python
from itertools import product

# Example use case: Generating all possible combinations of two dice rolls
dice1 = [1, 2, 3, 4, 5, 6]
dice2 = [1, 2, 3, 4, 5, 6]

# Generate all possible combinations of two dice rolls
all_combinations = list(product(dice1, dice2))

# Print the generated combinations
for combination in all_combinations:
    if sum(combination) == 9:
        print(combination)
```

# chain 
- combine 2 elements 

```python
from itertools import chain 

# Example use case: Combining and iterating over multiple lists 
list1 = [1, 2, 3] 
list2 = [4, 5, 6] 
list3 = [7, 8, 9] 

# Combine the lists into a single iterator 
combined_iterator = chain(list1, list2, list3) 

# Iterate over the combined iterator 
for element in combined_iterator: 
    print(element)

```

# islice

- just like slice in golang

```python
from itertools import islice 

# Example use case: Extracting a slice from a list 
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10] 

# Get a slice of the list from index 2 to 8 (exclusive) 
slice_result = islice(numbers, 2, 8) 

# Iterate over the slice and print the elements 
for element in slice_result: 
    print(element)
```

# compress

- act as filter

```python
from itertools import compress

# Example use case: Filtering elements based on selectors
data = ['a', 'b', 'c', 'd', 'e']

# Filter the elements from data based on the truthiness of selectors
filtered_result = compress(data, (d for d in range(0, len(data)) if d % 2 == 0))

# Iterate over the filtered result and print the elements
for element in filtered_result:
    print(element)
```


# count

^540805

- provides an iterator that generates an infinite sequence of numbers starting from a specified value and with a specified step size.


```python
from itertools import count 

start = 10 
# Starting value 

step = 2 
# Step size 

# Create the count iterator 
counter = count(start, step) 

# Print the first 5 numbers in the sequence 
for _ in range(5): 
	print(next(counter))
```


# Cycle

^b0210a

create cycle

```python
from itertools import cycle

iterable = ['A', 'B', 'C'] 
# Example iterable 

# Create the cycle iterator 
cycler = cycle(iterable) 

# Print the first 6 elements from the cycle 
for _ in range(6): 
	print(next(cycler))
```


# Repeat

^c11fa3


```python
from itertools import repeat

element = 'Hello'  # Example element
repeat_count = 3  # Number of repetitions

# Create the repeat iterator
repeater = repeat(element, repeat_count)

# Print the repeated elements
for item in repeater:
    print(item)

```

