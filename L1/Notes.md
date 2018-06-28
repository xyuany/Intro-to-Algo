Introduction
===
Analysis of algorithm: theoritical study of computer program performance and resource usage.<br>
    Correctness, simplicity, maintainability, stability, features, functinality, security, scalability are more important than performance.<br>
    performance decides feasibility. Performance is under the basics.<br>
## For example: Sorting
### insertion sort<br>
```C
Inserton.Sort(A,n)//Sorts A [1....n]
for j←1 to n
	do key←A[j]
		i←j-1
		while i>0 & A[i]>key
			do A[i+1] ← A[i]
			i ← i-1
		A[i+1] ← key
```
* example   
8 `2` 4 9 3 6<br>
2 8 `4` 9 3 6<br>
2 4 8 `9` 3 6<br>
2 4 8 9 `3` 6<br>
2 3 4 8 9 `6` <br>
2 3 4 6 8 9<br>
* running time: <br>
	* depands on input (already sorted)<br>
	* depands on input size (6 vs 600)   
		* parameterize in input size   
	* upper bonds running time   
		* guarantee to the user   
* kinds of analysis   
	* worst-cast(usually)   
	T(n) = max time on any input of size `n`  
	* average case   
	T(n) = expected time over all input of size `n`   
		need an assumption of statistical distribution of input (equally likely maybe)	
	* best-case analysis (bogus)   
* What is insertion sort's worst time?   
	* Depands on computer   
	- relative speed (on same machine)   
	- absolute speed (on diff machines) whatever machines   
* IDEA: asymptotic analysis
	* igmore machine dependant constants
	* look at **growth of T(n)** as n to infinitive
* asymptotic notation   
	* θ: drop low order terms and ignore leading constants   
	- Ex: 3n^3 + 90n^2 - 5n - 769 = θ(n^3)   
* Insertion sort analysis (worse case: input reverse sorted)   
	* counting memory references: how many times actually access some variables?   
	**T(n) = Σ(j:2,n)θ(j) = θ(n^2)**  (Arithmetic sequence)
	* for small `n`, fast   
	not at all for large `n`

### Merge sort
* merge sort A[1....n] step:   
	1. if n =1, done       
	2. recursive algorithm sort      
	A[1....(n/2)] and A[(N/2)+1....n]   			
	3. merge 2 sorted lists   
	key subroutine - Merge   
	 20  12    
	 13  11    
	 7   9 			
	 2   1    
	 1, 2, 7, 9 .....    
	 Time: θ(n) on n total elements!!(linear time)    

### Recursive Tree   
leave : n, θ(1)   
height: log(n)   
nodes: n   
T(n)=n*log(n) = θ(nlog(n))   
