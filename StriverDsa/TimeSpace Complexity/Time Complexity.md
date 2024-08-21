
Time complexity is not time taken for the program to run.

But it is the rate at which the time taken increase with the respect to the input size.



3 rules of when measuring time complexity:
- Always compare tc in terms of worst case scenario
- Avoid constants
- Avoid lower values



```
for (i = 1, i<= n ; i++){
	cout<<"Hey";
}

// here the code will run n times but will do 3 operations in each loop,  
so the bigO would be O(3n)
but as the rules says, we avoid constants so
the final tc of the code will be 
O(n)
```




## Types of Complexities

1. Big O: worst case , also called upper bond
2. Theta : average case
3. Omega: best case, also called as lower bond