---

---

# Are Anagrams

## Problem

Given 2 words, return `true` if both strings use the same characters (including duplicates) and `false` otherwise.

## Solutions

### [[Caching]]

```python
# T(n) S(n)
from collections import Counter

def areAnagrams(str1, str2):
    # by definition, anagrams must have the same length.
	if len(str1) != len(str2):
		return False
	# create a dictionary per string.
	counts1, counts2 = dict(), dict() # { char: freq }
  
	# for each string, cache each character's count.
    for char1, char2 in zip(str1, str2):
	    counts1[char1] = 1 + counts1.get(char1, 0)
		counts2[char2] = 1 + counts2.get(char2, 0)
        
    return counts1 == counts2 # check if each string's characters have equal counts.
	return Counter(str1) == Counter(str2) # shortcut.
```