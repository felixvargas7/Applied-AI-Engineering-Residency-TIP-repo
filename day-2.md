# Day 2

Problem:
leetcode link:

```js
//js solution
function maxProfit(prices) {
  let minPrice = Infinity;
  let maxProfit = 0;
  for (let i = 0; i < prices.length; i++) {
    if (prices[i] < minPrice) {
      minPrice = prices[i];
    } else if (prices[i] - minPrice > maxProfit) {
      maxProfit = prices[i] - minPrice;
    }
  }
  return maxProfit;
}
```

Input:
prices = [7,1,5,3,6,4]

Output:
5

Algorithm:

Python Solution:

```py
# solution here
def maxProfit(prices):
    min_price = float('inf')
    max_profit = 0
    for i in range(len(prices)):
      if prices[i] < min_price:
        min_price = prices[i]
      elif prices[i] - min_price > max_profit:
        max_profit = prices[i] - min_price
    return max_profit
```
