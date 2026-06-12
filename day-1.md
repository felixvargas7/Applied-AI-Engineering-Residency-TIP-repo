# Day 1

Problem: FizzBuzz

leetcode link: https://leetcode.com/problems/fizz-buzz/

```js
function fizzBuzz(n) {
  const result = [];
  for (let i = 1; i <= n; i++) {
    if (i % 15 === 0) {
      result.push("FizzBuzz");
    } else if (i % 3 === 0) {
      result.push("Fizz");
    } else if (i % 5 === 0) {
      result.push("Buzz");
    } else {
      result.push(String(i));
    }
  }
  return result;
}
```

Input: Integer

Output: Array of strings

Algorith:
Array used to store results of each string depending on conditions

Python Solution:

```py
# solution here
def fizzBuzz(n):
  result = []
  for i in range(n):
    if i % 15 === 0:
      result.append("FizzBuzz")
    elif i % 3 === 0:
      result.append("Fizz")
    elif i % 5 === 0:
      result.append("Buzz")
    else:
      result.append(i)
```
