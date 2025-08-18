Space optimization is important

Problem statement 

arr = [7, 1, 5, 3, 6, 4]

now array at 0 is day 1 array at index 1 is day 2 etc 
we need to buy the stock and sell it and also make sure that profit we obtain is highest

in above example we have buy - 1 and sell at -6 in this way our profit is max i.e 5

if u are selling on ith day u buy on minimum price day 
for every track keep track of minimal at left


minimum = a [0], profit = 0
for ( i =1; i<n;i++ {
cost = a[i] - min;
profit = max (profit, cost)
mini = min (mini, a[i])
}

TC : O(n)
SC: O(1)


## Best Time to Buy and Sell Stock

**Problem:** Find the maximum profit from buying and selling a stock once, where you must buy before you sell.

### Approach:

The key insight is: for each day, calculate the profit if we sell on that day (current price - minimum price seen so far). Keep track of the maximum profit.

### C++ Pseudocode:

```cpp
int maxProfit(vector<int>& prices) {
    if (prices.empty()) return 0;
    
    int minPrice = prices;
    int maxProfit = 0;
    
    for (int i = 1; i < prices.size(); i++) {
        // Profit if we sell today
        int profit = prices[i] - minPrice;
        
        // Update maximum profit
        maxProfit = max(maxProfit, profit);
        
        // Update minimum price seen so far
        minPrice = min(minPrice, prices[i]);
    }
    
    return maxProfit;
}
```

### Explanation:

1. **Initialize:**
    
    - `minPrice = prices`: Start with first day's price as minimum
    - `maxProfit = 0`: No profit initially
2. **For each day (starting from day 2):**
    
    - Calculate profit if we sell today: `current price - minimum price so far`
    - Update `maxProfit` if this profit is higher
    - Update `minPrice` if today's price is lower (potential better buying day)
3. **Why it works:**
    
    - We're essentially checking every possible selling day
    - For each selling day, we pair it with the best (lowest) buying day before it
    - This ensures we find the maximum profit possible

### Example Walkthrough:

```
arr = [7, 1, 5, 3, 6, 4]

Day 1: price=7, minPrice=7, maxProfit=0
Day 2: price=1, profit=1-7=-6, maxProfit=0, minPrice=1
Day 3: price=5, profit=5-1=4, maxProfit=4, minPrice=1
Day 4: price=3, profit=3-1=2, maxProfit=4, minPrice=1
Day 5: price=6, profit=6-1=5, maxProfit=5, minPrice=1
Day 6: price=4, profit=4-1=3, maxProfit=5, minPrice=1

Result: Buy at 1, Sell at 6, Profit = 5
```

**Time Complexity:** O(n) - single pass through array  
**Space Complexity:** O(1) - only using constant extra space




 