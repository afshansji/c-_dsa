Maximum subarray sum

Subarray -> Contiguous part of the array

arr = [-2, -3, 4, -1, -2, 1, 5, -3]

ans = 7


One approach will be traverse all subarrays  
start from index 0 traverse all sub arrays 
1, ,2 ,3 , 4, 5
again start from index 1 and do the same for all


maximum = int_min
for i =0; i<nl i++ {
for j=i;j<n;j++{

sum = 0
for k = i -> j {
sum+= arr [k]

maximum = max (sum, maximum )
}
}
}

TC -> O n^3
SC -> O (1)


Better solution:
Dont need to iterate again from begining 
Whatever was the sum of previous subarray jus add it to the current index
 


maximum = int_min
for i =0; i<nl i++ {
for j=i;j<n;j++{

sum = 0
sum+= arr [j]

maximum = max (sum, maximum )
}
}
}

TC: O n^2
SC: O(1)

Optimal solution:
Kadanes algorithm 

Initialise 2 
max = int_min
sum = 0

take first element carry forward to the next element if its negative dont take sum if its sum>0 take sum to the next
at each step compare max and sum if sum > max update max 
by the end ur max will have max value of subarray
if negative make sum =0 again
in that problem if none is giving positive make it 0

FOR PRINTING ?INTERVIWER MIGHT ASK AGAIN

if (sum == 0) start =i i.e we are  starting and intialise maxStart = -1 and maxEnd = -1
and then when we get max maxstart = start and maxEnd = i and then we can print 




Kadane's Algorithm is a popular method to find the maximum sum of a contiguous subarray in an array. It efficiently reduces the time complexity to O(n) by using a dynamic programming approach.

### Explanation:

1. **Initialize Variables:**
    
    - `maxSum`: This will store the maximum sum found so far. Initialize it with the smallest possible integer value.
    - `currentSum`: This keeps track of the current subarray sum. Start with 0.
2. **Iterate Through the Array:**
    
    - For each element, add it to `currentSum`.
    - If `currentSum` exceeds `maxSum`, update `maxSum`.
    - If `currentSum` becomes negative, reset it to 0. This is because a negative sum would decrease the potential for a larger sum in subsequent elements.
3. **Tracking Indices (Optional):**
    
    - To track the start and end indices of the maximum subarray:
        - Use variables `start`, `end`, and `tempStart`.
        - Update `start` when `currentSum` is reset.
        - Update `end` whenever `maxSum` is updated.

### Pseudocode in C++:

```cpp
#include <iostream>
#include <vector>
#include <climits> // For INT_MIN

int maxSubArraySum(const std::vector<int>& arr) {
    int maxSum = INT_MIN;
    int currentSum = 0;
    int start = 0, end = 0, tempStart = 0;

    for (int i = 0; i < arr.size(); ++i) {
        currentSum += arr[i];

        if (currentSum > maxSum) {
            maxSum = currentSum;
            start = tempStart;
            end = i;
        }

        if (currentSum < 0) {
            currentSum = 0;
            tempStart = i + 1;
        }
    }

    std::cout << "Maximum Subarray Sum: " << maxSum << std::endl;
    std::cout << "Subarray Indices: [" << start << ", " << end << "]" << std::endl;
    
    return maxSum;
}

int main() {
    std::vector<int> arr = {-2, -3, 4, -1, -2, 1, 5, -3};
    maxSubArraySum(arr);
    return 0;
}
```

### Key Points:

- **Efficiency:** Kadane’s algorithm runs in linear time, O(n), making it optimal for this problem.
- **Dynamic Programming Insight:** The algorithm builds up solutions to subproblems (subarrays ending at each index) to solve the overall problem.
- **Handling Negatives:** By resetting `currentSum` to zero when it becomes negative, we ensure that future sums are not adversely affected by past negative values.

This approach is like walking through a path and only carrying forward positive gains, dropping any baggage that pulls you down.

