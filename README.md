# DSA-Ransom-Note
Given two strings ransomNote and magazine, return true if ransomNote can be constructed by using the letters from magazine and false otherwise.

Each letter in magazine can only be used once in ransomNote.

```
Input: ransomNote = "a", magazine = "b"
Output: false
```
```
from collections import Counter
class Solution:
    def canConstruct(self, ransomNote: str, magazine: str) -> bool:
        #Use build in function to count key, values in each input string
        ransomnote_counts=Counter(ransomNote) # Time cost O(n)
        magazine_counts=Counter(magazine) # Time cost O(m)
        for char,count in ransomnote_counts.items(): # Time cost of iteration O(n)
            magazine_count=magazine_counts[char] # O(1)
            if magazine_count < count: # O(1)
                return False
        return True
    '''
    Since m should be always higer or equal to n then we can simplify O(n)=O(m)
    Total time cost O(m) + 2O(n) = 3O(m) = O(m)
    Total space cost for bulided 2x hashMaps we use O(k), however since only possible letters are 26 combination threfore can be simplify to O(1)
    '''
```
