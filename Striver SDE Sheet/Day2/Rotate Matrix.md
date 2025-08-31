Rotate Matrix/Image by 90 Degrees

**Example 1:**

![](https://assets.leetcode.com/uploads/2020/08/28/mat1.jpg)

**Input:** matrix = [[1,2,3],[4,5,6],[7,8,9]]
**Output:** [[7,4,1],[8,5,2],[9,6,3]]

**Example 2:**

![](https://assets.leetcode.com/uploads/2020/08/28/mat2.jpg)

**Input:** matrix = [[5,1,9,11],[2,4,8,10],[13,3,6,7],[15,14,12,16]]
**Output:** [[15,13,2,5],[14,3,4,1],[12,6,8,9],[16,7,10,11]]


Bruteforce :
wee declare an nxn matrix where we will store the answer 
After doing observations we can say that 
we have i and j -> i and j 

![[Pasted image 20250831211451.png]]

intution and observation that j will be colum wise i always 

and for the other we can have a formula 

0 -> 3
1 -> 2
formula: i -> (n-1) - i

![[Pasted image 20250831211604.png]]


ans [ n ] [ n ]

for ( i = 0-> n) {
for (j = 0 -> n) {


arr [  j   ]   [  n - 1   - i   ] = matrix [     i    ]  [    j    ]

}
}

TC:  O (n sqaure)
SC:  O ( n square) since external 2d matrix

Optimal:
Observe 

step 1
we can see 1 column is 1st row but in reverse order 
2nd column is in 2nd row but in reverse order 
similarly for all 

We need to transpose matrix 
row becomes column and column becomes row that is what transpose is 

step 2
now reverse every row done


now how can we transpose a matrix 
even this is simple 
if u notice diagnals stay where they are and matrix i, j is jus swapped with j, i 
the matrix positions:
0 1 -> 1 0
2 3 -> 3 2

here as well for 1st row we go to  3 and for 2nd row we got from 2 -> 1 etc observe 


hence:

![[Pasted image 20250831213253.png]]


then we reverse the row 

1st line of code is to find size of matrix 
![[Pasted image 20250831213347.png]]
TC: first and second loop for both transpose is n/2
and reverse n/2