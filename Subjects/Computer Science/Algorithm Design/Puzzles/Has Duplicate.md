---

---

# Has Duplicate

## Problem

Given an array of values, return `true` if any value appears more than once and `false` otherwise.

## Solutions

### [[Two Pointers]]

```python
# T(n^2) S(1)
def hasDuplicate(array):
	for i in range(0, len(array)): # compare each value
		for j in range(i+1, len(array)): # to the rest of the values
			if array[i] == array[j]: # to check for equal values.
				return True
	return False
```

### [[Sorting]]

```python
# T(nlogn) S(1)
def hasDuplicate(values):
	sorted_values = sorted(values) # sort the values
	for i in range(1, len(values)): # to compare each value
		if sorted_values[i] == sorted_values[i-1]: # to its consecutive value.
			return True
	return False
```

### [[Caching]]

```python
# T(n) S(n)
def hasDuplicate(values):
	cache = set()
	for value in values: # for each value,
		if value in cache: # check if the value was cached,
			return True
		record.add(value) # then cache that value.
	return False
```

### [[Algorithm Design/Techniques/Definition]]

By definition, an array with a duplicate value must have more values than how many unique values the array has.

```python
# T(n) S(n)
def hasDuplicate(array):
	unique_values = set(array) # cast the array as a set
	return len(array) != len(unique_values) # and check their lengths.
```