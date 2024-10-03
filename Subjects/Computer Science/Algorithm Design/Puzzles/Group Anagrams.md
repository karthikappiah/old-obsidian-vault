---

---

# Group Anagrams

## Problem

Given an array of words, group the anagrams in any order.

## Solutions

### [[Bucketing]]

```python
# T() S()
from collections import Counter, defaultdict

def groupAnagrams(strings):
	# create a dictionary with an empty list as the default.
	anagrams = defaultdict(list) # { count: [strings] }
	
	for string in strings: # for each string,
		counts = [0] * 26
		for character in string: # record each character's count to
			index = ord(character) - ord("a")
			counts[index] += 1
		key = tuple(counts) # (keys must be hashable)
		anagrams[key].append(string) # group the string by character count,
	
	return anagrams.values() # then return the grouped strings.
```