# Best Time to Buy and Sell Stock

**Difficulty:** Easy  
**Topic:** Arrays, Greedy Algorithm  

---

## 🧠 Problem Statement

You are given an array `prices` where `prices[i]` is the price of a stock on the `i`th day.

You want to maximize your profit by choosing:
- one day to **buy** a stock
- a different future day to **sell** that stock

Return the maximum profit you can achieve.  
If no profit is possible, return `0`.

---

## 🧪 Example

Input: prices = [7,1,5,3,6,4]
Output: 5
Explanation: Buy at price 1 and sell at price 6 → profit = 5

---

## 💡 Approach (Optimized)

This solution uses a **Greedy Algorithm** with a **single pass**.

### Key Idea:
- Track the **minimum price seen so far** (best day to buy)
- At each day, calculate the profit if we sell on that day
- Update the maximum profit whenever a better profit is found

We never look back, only forward.

---

## 🧾 JavaScript Solution (Optimized)

```js
var maxProfit = function(prices) {
    let minPrice = prices[0];
    let maxProfit = 0;

    for (let i = 1; i < prices.length; i++) {
        if (prices[i] < minPrice) {
            minPrice = prices[i];
        } else {
            let profit = prices[i] - minPrice;
            if (profit > maxProfit) {
                maxProfit = profit;
            }
        }
    }

    return maxProfit;
};