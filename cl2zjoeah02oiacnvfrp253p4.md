## 121. Best Time to Buy and Sell Stock | Arrays

Hey, today we are going to solve one of the famous interview problems that may be asked to you, i.e **Best Time to Buy and Sell Stock**.  This question comes under Array concepts. Let's understand what the problem is and how to find its solution.

* Problem link: [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

## Problem Statement
You are given an array `prices` where `prices[i]` is the price of a given stock on the `i`<sup>`th`</sup> day.

You want to maximize your profit by choosing a **single day** to buy one stock and choosing a **different day in the future** to sell that stock.

Return *the maximum profit you can achieve from this transaction*. If you cannot achieve any profit, return `0`.


## Examples
Here are some sample examples through which you can understand the problem clearly.
**Example 1:**
<pre>
Input: prices = [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.
</pre>

**Example 2:**
<pre>
Input: prices = [7,6,4,3,1]
Output: 0
Explanation: In this case, no transactions are done and the max profit = 0.
</pre>

**Example 3:**
<pre>

</pre>

## Constraints
* 1 <= prices.length <= 10<sup>5</sup>
* 0 <= prices[i] <= 10<sup>4</sup>

## Solution
So, we looked into all the problem details and constraints. Now let's dive into solutions for the same.

1. The intuition behind this problem is, that we will traverse the given array to find the minimum element. If the current element is smaller than the previous minimum element, we will update the previous minimum.
2. When we get the minimum element, we will calculate the `profit` at that price element `(prices[i]-mini)`
3. If profit is maximum at that element, then we will update the value of `profit` (we want maximum profit).
4. At last we will return the maximum profit generated.

```
// C++ Solution
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int mini = INT_MAX;
        int profit = 0;
		
        for(int i=0;i<prices.size();i++){
            mini = min(mini, prices[i]);
            profit = max(profit, prices[i]-mini);
        }
        
        return profit;
    }
};
```

## Conclusion
So, this was the solution for the ** Best Time to Buy and Sell Stock** Leetcode Problem. Hopefully, you might understand this solution. If you found it useful, please follow me for more such articles and do share with your peers. And yes, don't forget to leave your suggestions, and thoughts in the comment box. 

Thank you!
