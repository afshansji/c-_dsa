
Problem statement 
U will be given an array of mxn with only 0 and 1
what u need to do is whichever 0 are present in array mark the row and column all as 0
similarly do for all initial 0s in the mxn array

1. Bruteforce
   iterate entire matrix 
   when u reach zero mark entire row and column as -1 if u see 0 keep it as zero 
   similarly iterate entire array once done 
   again traverse entire array now convert -1 to 0 
   done!


for i =0; i<n;i++ {
for j=0; j<m: j++ {
if arr[i][j] == 0 {
markRow(i) //go to ith row and mark
markRow(j)
}
}
}

markRow (i) {

for j =0 j<m;j++ {
if arr[i][j] != 0 {
arr [i][j]] =-1
}
}
}


markRow (j) {

for i =0 i<n;i++ {
if arr[i][j] != 0 {
arr [i][j]] =-1
}
}
}

for i =0; i<n;i++ {
for j=0; j<m: j++ {
if arr[i][j] == -1 {
arr[i][j] =0
}
}
}

TC: O(nxm) (n+m) O(nxm)
n^3

2. Better solution
   Instead of marking all column and rows as -1 or 0 we will keep track of that row and column no and at the end of iteration mark them as 0 since anyways itll be 0 that row and column right 

![[Pasted image 20250820000530.png]]

So we will make a new m size column and n size row 
traverse the matrix first assign all rows and columns as 0 and if the i,j contains 0 mark that row and column as 1 
once iteration complete again traverse the entire array and mrk them as 0 simple 

col [m] = [0]
row [n] = [0]

for i =0->n {
for j = 0->m {
if arr [i][j] == 0 {
row [i] =1
row [j] =1
}
}
}

for i =0->n {
for j = 0->m {
if row [i] || col [j] == 1 {
a[i] [j] =0
}
}}

TC: 2nm = n^2
SC: O(n) = O(m)

since max tc for 2d array is n^2 we will focus to imrpove SC

3. Optimal

![[Pasted image 20250820003103.png]]

edge case helpful:
left corner can never be 0
deal with the newly created section at end
dont touch first rows and columns 


