# Day 3

Problem: Reverse String
leetcode link:

```js
//js solution
function reverseString(s) {
  let left = 0;
  let right = s.length - 1;
  while (left < right) {
    let temp = s[left];
    s[left] = s[right];
    s[right] = temp;
    left++;
    right--;
  }
  return s;
}
```

Input:
s = ["h","e","l","l","o"]

Output:
["o","l","l","e","h"]

Algorithm:
Looping through the array of strings
Using push method to create new array of strings that pushes each value starting at the beginning,
Return that array after

Python Solution:

```py
# solution here
def reverseString(s):
    left = 0
    right = len(reverseString) - 1

```

Problem:
leetcode link:

```js
//js solution
function lengthOfLongestSubstring(s) {
  let seen = {}; // object/hash map that lets us note which letters have been seen
  let left = 0; // declaring variable for index of first character, starting point
  let maxLength = 0; // declaring variable to determine max length of substring, that doesn't repeat
  for (let right = 0; right < s.length; right++) {
    // loop through, keeping track through loop
    if (seen[s[right]] !== undefined && seen[s[right]] >= left) {
      left = seen[s[right]] + 1; // adding to hashmap if we repeat
    }
    seen[s[right]] = right;
    maxLength = Math.max(maxLength, right - left + 1); // add to maxLength
  }
  return maxLength;
}
```

Input:
s = ["h","e","l","l","o"]

Output:
["o","l","l","e","h"]

Algorithm: Sliding Window
Looping through the array of strings
Using push method to create new array of strings that pushes each value starting at the beginning,
Return that array after

Python Solution:

```py
# solution here
def reverseString(s):
    seen = {}
    left = 0
    maxLength = 0
    for i in range(len(s)):
        if seen[s[right]] !== None && seen[s[right] >= left]:
            left = seen[s[right]] + 1
        seen[s[right]] + 1
        maxLength = max(maxLength, right - left + 1)
    return maxLength

```
