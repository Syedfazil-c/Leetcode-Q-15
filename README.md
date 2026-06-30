Best Time to Buy and Sell Stock

Problem

You are given an array prices where prices[i] is the price of a stock on the ith day.

You can buy the stock only once and sell it only once.

Return the maximum profit you can achieve.

If no profit is possible, return 0.

Approach

- Initialize min_price as infinity to keep track of the lowest stock price seen so far.
- Initialize max_profit as 0.
- Traverse the prices array.
- If the current price is lower than min_price, update min_price.
- Otherwise, calculate the profit by subtracting min_price from the current price.
- If the calculated profit is greater than max_profit, update max_profit.
- After traversing the entire array, return max_profit.

Complexity

Time Complexity: O(n)

Space Complexity: O(1)

Key Insight

Keep track of the lowest buying price while traversing the array.

For every new price, calculate the profit if you sell on that day.

Update the maximum profit whenever a better profit is found.

Example

Input:

prices = [7,1,5,3,6,4]

Output:

5

Explanation:

Buy at price 1 (Day 2)

Sell at price 6 (Day 5)

Profit = 6 - 1 = 5

Input:

prices = [7,6,4,3,1]

Output:

0

Explanation:

The stock price keeps decreasing.

No profit can be made, so return 0.

Code

def maxProfit(prices):

    min_price = float('inf')
    
    max_profit = 0

    for price in prices:
    
        if price < min_price:
        
            min_price = price
        else:
        
            profit = price - min_price
            
            if profit > max_profit:
            
                max_profit = profit

    return max_profit


