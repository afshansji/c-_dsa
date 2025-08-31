Type: Medium
As we know permutation is combinations 
eg: arr [] = [3 1 2]
3! = 6 ways 

123, 231, 312 etc

We need to do next permuation in sorted order
i.e 123, 132,213, such way
when we reach end i.e 321 go back to 123

**Input:** nums = [1,2,3]
**Output:** [1,3,2]

in interview jus tell approach as its lonnnger
Bruteforce:
1. Generate all permutations in sorted order
2. Do linear search 
3. We find input-> next will be our answer
TC: N! X N extremely long if 15 length 15! = vv long

Better we can use stl in c++ 
we have next_permutation stl which will make our work easier 

next_permutation(a.begin, a.end 
return a;
)
itll return next permuation from list 

Optimal Solution:
1.
All about observation -> dictionary -> we need to find breakpoint at a time there will be breakpoint 12345 here soon after 5 there will be dip
eg: 2154300 we go on reducing prefix
we see after 5 we have 1 which is breakpoint 
we need to start from lhs ok
in short:
Find largest prefix until breakpoint
only in last i.e 54321 there wont be any dip

2.
also we need to see jus largest number after the breakpoint i.e 1

3.
After that place the remaining numbers in sorted order

TC: O(3n)
SC: O(1) sicne array not modified


 









