Type: Hard
1 at all sides and then middle elements add the numbers

![[Pasted image 20250820220342.png]] 

We can get multiple types of problems in pascal 
1. given row =5 and column =3 find element at row = 5 and column =3 => ans: 6
2. Print any nth row of pascal triangle if N =5 print 1, 4, 6, 4, 1
3. Given N, print entire pascal triangle, print entire 6 rows pascal triangle
   
   
   now solution for 1 we have a formula 
	R-1 C(combination) C-1
	i.e nCr = n! / r! x (n-r)!
	4C2 = 6
There is a shortcut to find nCr we will use it 
7C2 = since 2 we will go down as 2 x 1 hence on top we will do 7 x 6 x 5!
last will get cut and only 7 x 6/ 2 x 1 remains 


similarly for 10c3 = 10 x 9 x 8 / 3 x 2 x 1 done rest all gets cancelled

and also in code divide first by 1 and then 2 and then 3 and so on 
TC = o(r)
SC = O(r)


func ncr(r-1, n-1 )

and pseducode

func ncr (n,r) {
res = 1
for i =0 i<r ;i++ {
res = res x (n-i) 
res = res/(i+1)
}
return res
}


2. Observe = nth row wil have n elements since 5th row has 5 elemtnts etc

run for loop for c=1; c<=m;c++ {
print funcncr(n-1, c-1)
}

TC: O(N x R)

Formula: R-1 C C-1

![[Pasted image 20250820224201.png]]

notice the image, we are adding 1 and 2s consistently

lets think of 1 formula but we know always first and last element in the row will be 1

 
formula will be ans x (row - col) /col

pseducode :

for i=1;i<n;i++ {
ans = ans (n-i)
ans = ans / (i)
print ans 
}

TC: O(n), SC: O(1)

3.
![[Pasted image 20250820224759.png]]
Brutrforce : 

for row = 1->n {
templist = []
for col = 1->row {
yemplist .add (funcncr(row-1, col-1))
}
ans.add(templist)
}

TC: O(n^3)

Better solution is use type 2 to get elements of each row and do for all