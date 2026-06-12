# Day 5

Problem:
leetcode link:

```js
//js solution
function threeSum(nums) {
  const result = [];
  nums.sort((a, b) => a - b);
  for (let i = 0; i < nums.length - 2; i++) {
    if (i > 0 && nums[i] === nums[i - 1]) continue;
    let left = i + 1;
    let right = nums.length - 1;
    while (left < right) {
      const sum = nums[i] + nums[left] + nums[right];
      if (sum === 0) {
        result.push([nums[i], nums[left], nums[right]]);
        while (left < right && nums[left] === nums[left + 1]) left++;
        while (left < right && nums[right] === nums[right - 1]) right--;
        left++;
        right--;
      } else if (sum < 0) {
        left++;
      } else {
        right--;
      }
    }
  }
  return result;
}
```

Input: Array of numbers

Output: Array of array of numbers

Algorithm:
We want to return an array with arrays of 3 numbers.
We get these triplet arrays by first finding which three indexes of numbers in the original array have a sum equal to 0.
After that, form a triplet that contains these three numbers summing to 0.
It is important that no duplicates be in the triplet.

Python Solution:

```py
# solution here
class Solution:
    def threeSum(self, nums: list[int]) -> list[list[int]]:
        result = [] #creating list for result
        nums.sort((a,b) => a - b) #sorting array by default ascending order
        for i in range(len(nums) - 2): #for loop going through the nums list, subtracting 2 from length
            if i > 0 and nums[i] === nums[i - 1]
                continue
            left = i + 1
            right = nums.length - 1

```
