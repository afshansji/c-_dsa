**Example 1:**

**Input:** intervals = [[1,3],[2,6],[8,10],[15,18]]
**Output:** [[1,6],[8,10],[15,18]]
**Explanation:** Since intervals [1,3] and [2,6] overlap, merge them into [1,6].

**Example 2:**

**Input:** intervals = [[1,4],[4,5]]
**Output:** [[1,5]]
**Explanation:** Intervals [1,4] and [4,5] are considered overlapping.

**Example 3:**

**Input:** intervals = [[4,7],[1,4]]
**Output:** [[1,7]]
**Explanation:** Intervals [1,4] and [4,7] are considered overlapping.

![[Pasted image 20250831235502.png]]

lets keep all closer interal together

bruteforce:
1. Sort the arrays 
 1,3 2,4 2,6 8,9 8,10 9,11 15,18 16,17

now iterate the array:
check 1,3 and 2,4 
2 is less or equal to 3 hence we club them and make 1, 4
next check 1, 4  and 2,6 sine 2 is less than 4 clun them as well 
now we have is 1, 6
next 1,6 and 8,9 8 is larger move the pointer from 1,3 to 2,4 but its already there now next move to the same and as we compare we get clubbed subintervals 
1,6 and 8,11 and 15,18
TC: Nlogn + O(2n)
SC: O(n)

Optimal:
Its the same but we avoid traversing the array twice like we did in bruteforce solution 
keep on checking with the previous interval and dont revisit once done 
TC: O(n)
SC: O(n)




