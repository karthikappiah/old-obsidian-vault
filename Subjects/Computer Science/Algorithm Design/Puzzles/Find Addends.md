---

---

# Find Addends

## Problem

Given an array of integers `numbers` and an integer `target`, return the indexes for the pair of addends that add up to `target`.

## Solutions

### [[Caching]]

```python
# T(n) S(n)
def findAddends(numbers, target):
	record = dict()
	
	# for each number,
	for i, number in enumerate(numbers):
		# calculate its addend, then
		addend = target - number
		
		# check if its addend was cached,
		if addend in record:
			return (i, seen[addend])
			
		record[number] = i # then cache the number's value by its index.
	return ()
```