U will be given an array of 0 1 2 and tell to sort 

One bruteforce solution is use some sorting like merge sort sort done 
TC: O(NlogN), SC : O(N)

Better solution:
1, Declare 3 var 
count 0, count1, count2
increment it as u encounter 1, 2, 0 
at the end iterate the array overwrite existing elemts with 0 number of times 0 came 
overwrite 1 number of times 1 came
overwrite 2 number of times 2 came

for i =0; i<n; i++ {
if a[i] == 0 count0++
if a[i] == 1 count1++
if a[i] == 2 count2++

}

for (i=0;i<count0: i++) a[i] = 0
for (i=count0;i<count1: i++) a[i] = 1
for (i=count0 + count1;i<n: i++) a[i] = 2

TC: O(2n) SC: O(1)

Optimal Solution:
Dutch National Flag Algorithm

3 rules of algorithm:
1. [0........low-1] will be 0 i.e extreme left
2. [low........mid-1] will be 1
3. [high+1........n-1] will be 2 i.e extreme right

