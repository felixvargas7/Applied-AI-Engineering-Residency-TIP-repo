# Day 10

Problem: Running Sum of 1d Array

leetcode link: https://leetcode.com/problems/running-sum-of-1d-array/

```js

```

Input: list of integers

Output: list of integers (with running sum replacing every number after the first)

Algorithm:
We want to declare a variable holding the running sum
We loop through the numbers, and have a running sum that holds a sum after the loop keeps going: - this means that once we're on the second iteration, we want to have added the first index to the current, then have that value represent the running sum

On the third loop we add the running sum to the current index, then add that result into the running sum and continue

Since the problem wants to return a list with these running sums, we also want to on each iteration append that value into a new list

Python Solution:

```py
# solution here
#       running sum list declared empty
#       sum delcared
#
#       loop through nums
#           if i == 1:
#               append index value to running sum list
#               also add value of index to sum
#           elif:
#               add value of index to sum
#               THEN append that sum to list
#
#       return running sum list
#

class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        running_sum_list = []
        current_sum = 0

        for i in range(len(nums)):
            if i == 0:
                running_sum_list.append(nums[i])
                current_sum += nums[i]
            else:
                current_sum += nums[i]
                running_sum_list.append(current_sum)
        return running_sum_list

```

Problem: Maximum Number of Vowels in a Substring of Given Length

leetcode link: https://leetcode.com/problems/maximum-number-of-vowels-in-a-substring-of-given-length/description/

```js

```

Input: string, integer

Output: integer

Algorithm:
We want to make a set that first has the vowels we are checking for
We also want a variable that holds the result

After that, we want to loop through the array, in a sliding window fashion so we are able to catch all possible substrings with length equal to k
On each window, we want to check if the strings match, with each new character entering the window to be added to the right, and first character of the window

When we have a window with the proper length (k), we want to check for vowels using our set, and then if the number of vowels are more than the current result number, overwrite.

Keep going until we reach the end

Python Solution:

```py
# solution here
#       result = 0 to initialize
#           if length of k > length of s:
#               return result
#       vowels = set("aeiou")
#       window_count = empty Counter
#
#       window_size = k
#
#       for i from 0 to length of s - 1
#           # adding the charcter to the right (neighbor)
#           add s[i] to window_count
#
#           # once window > p, drop character on the left
#           if i >= window_size:
#               left_char = s[i - window_size]
#               decrement window_count[left_char]
#               if window_count[left_char] == 0:
#                   remove left_char from window_count
#
#           # when window = k, we do our checks of seeing if vowels are in the window, and count how many
#           if window_count == k:
#               if text.lower() in vowels()
#                   + 1 for each vowel in the substring, then add to result
#
#       return result

from collections import Counter

class Solution:
    def maxVowels(self, s: str, k: int) -> int:
        result = 0
        if k > len(s):
            return result
        vowels = set("aeiou")
        window_count = Counter()

        window_size = k

        for i in range(len(s)):
            window_count[s[i]] += 1

            if i >= window_size:
                left_char = s[i - window_size]
                window_count[left_char] += -1
                if window_count[left_char] == 0:
                    del window_count[left_char]

            if i >= window_size - 1:
                vowel_count = 0
                for char in window_count:
                    if char.lower() in window_count:
                    vowel_count += 1

        return result

```
