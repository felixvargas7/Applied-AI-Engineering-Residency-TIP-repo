# Day 4

Problem: Group Anagrams
leetcode link:

```js
//js solution
function groupAnagrams(strs) {
  const map = {}; // Hash map to keep track of anagrams
  for (let i = 0; i < strs.length; i++) {
    // loop through array strs
    const key = strs[i].split("").sort().join(""); // variable to take each index, split letters, sort by alphabetical order, and then rejoin them ("bat" -> b, a, t -> a, b, t -> "abt")
    if (map[key] === undefined) {
      // if a certain string doesn't exist
      map[key] = []; // create a key with that string
    }
    map[key].push(strs[i]); // push each string index into the key the key if it does exist
  }
  return Object.values(map); // return the values of each key in map
}
```

Input: array of strings

Output: array of array of strings

Algorith:
strs = ["eat","tea","tan","ate","nat","bat"]

       [["bat"],["nat","tan"],["ate","eat","tea"]]

We take in an array of strings, and we want to group the anagrams of these strings in an array grouping each, all within an array

Python Solution:

```py
# solution here
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        anagram_map = {} #hash map to hold anagrams
        for i in range(len(strs)): #looping through anagrams
                key = "".join(sorted(strs[i])) #splitting, sorted and joining back each element in strs list
                if key not in anagram_map: #checking if key is in the dictonary map
                    anagram_map[key] = [] #if  not, adding it to map as an empty array
                anagram_map[key].append(strs[i]) #then adding the element into the key as value, making sure to append the actual index (strs[i]) INSTEAD of just the number (i)
        return list(anagram_map.values())  #returning values of map, the list of lists showing anagrams grouped
        # note: the classic "map.values()" does not work in python, as it returns dictionary values, whereas this problem asks for List[List[strs]],
        # the solution: return the dictionary values, within a list()


```
