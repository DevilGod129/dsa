
Brute Force Solution by me: 
```
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        present =[]
        for i in nums: 
            if i in present: 
                return True
            else :
                present.append(i)
        return False
```

The above solution has 
    Final complexity
    Time: O(n²) worst case
    Space: O(n) worst case, because present may store every element

Better solution is :

    Using set: 
```
    class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        hashset = set()

        for n in nums: 
            if n in hashset: 
                return True
            hashset.add(n)
        return False


        which gives time complexity: 
        Set lookup and insertion are O(1) average, giving:

            Time: O(n) average
            Space: O(n)

```