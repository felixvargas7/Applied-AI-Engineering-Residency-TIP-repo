# Day 6

Problem:
leetcode link:

```js
//js solution
/**
 * @param {number[]} nums
 * @return {number}
 */

/* 
Buyour Method:
Using a candidate number within an array, and a counter to keep track of the majority element, we eliminate the need of a hash map to store all values of an array, instead opting for a since variable keeping track of the current majority through logic below:
*/
var majorityElement = function (nums) {
  let counter = 0; // set counter equal to 0. This variable will see how frequent the candidate for majority element is in the array
  let candidate = null; // set candidate equal to null. Variable keeping track of the current candidate for majority element. We want to update this as we iterate through the array if needed
  for (const num of nums) {
    // looping through each index in nums array
    if (counter === 0) {
      // conditional checking if counter is 0. Important because if counter is 0, that either means we are at the beginning of iterating, or a candidate has been neutralized (eg. if a "1" shows up first, and adds count to counter, and then a "2" shows up, counter will decrement so it goes back to 0)
      candidate = num; // if we see the counter is 0, we want to assign the current index we are on as the candidate
    }
    counter += num === candidate ? 1 : -1; // ternary operator, incrementing value of counter. It first checks if the candidate is equal to the current index. If it is, we are adding by 1 to the counter to indicate that the candidate increases in frequency. If candidate is not equal to the current index, we are adding -1 to the counter (or decrementing), to show that the frequency has decreased. This logic is what will determine if a candidate is the majority element or not.
  }
  return candidate; // once done iterating, we want to simply return the candidate that is the majority element, as our logic already handled which candidate is the majority
};
```

Input:
Array

Output:
Integer

Algorithm:
Buyour method. Checking a candidate and it's count (frequency)

Declaring variable for count, and candidate

Looping through array to update candidate.

Logic:
We start with no candidate, and the first iteration index is assinged as the value to candidate, because the count starts at 0 and we check if the count is zero.

We then check to see if curent index is equal to the candidate, if so, we increment counter, if not, we decrement counter.

After iterating through entire array, we simply return candidate as it holds the majority element

Python Solution:

```py
# solution here
# Buyuor Method
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        counter = 0 # declaring counter, keeping track frequency of number
        candidate = None; # declaring candidate, keeping track of the number that counter frequency keeps track of
        for num in nums: # looping through list nums
            if counter == 0: # conditional checking if counter is 0, either at beginning of iteration, or if candidate is nullified
                candidate = num # assigning candidate to equal current index if counter is 0
            counter += 1 if num == candidate else -1 # logic checking if current index is candidate, if so add 1, if not subtract 1. Each time the current index matches the candidate, we add 1 to show its majority increasing, and each time current index doesn't match candidate we remove 1 to show the majority decreasing. If we get to 0 at the next iteration, we set the current index as the candidate.
        return candidate # returning candidate after iteration
```
