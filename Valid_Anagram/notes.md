

Solution by me: 
This is wrong as doesnt count the no of times a string is in the letter: 
```
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        n1 = list(s)
        n2 = list(t)
        for i in n2:
            if i in n1:
                pass
            else:
                return False
        return True

```

The complexities are: 
     # Time complexity  = O(n2) ![alt text](image-1.png)
     # Space Complexity = O(n+M) ![alt text](image.png)
 


The better solution: 

```
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
       #return Counter(s) == Counter(t) # juggad

        if len(s) != len(t):
            return False
        countS, countT ={} , {}

        for i in range(len(s)):
            countS[s[i]] = 1 + countS.get(s[i],0)
            countT[t[i]] = 1 + countT.get(t[i],0)
        for c in countS:
            if countS[c] != countT.get(c,0):
                return False
        return True
```

        Time complexity: O(n)
        Space complexity: O(n)

        Explanation of variables:

        n: length of strings s and t
        countS, countT: dictionaries storing character counts