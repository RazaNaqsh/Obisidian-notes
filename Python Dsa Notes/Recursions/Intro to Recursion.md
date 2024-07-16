a way of solving a problem by having a function calling itself
Breaks the problem into smaller subproblems , repeat until you get to the lowest level of problem

### Properties
- Same operations is being performed with different inputs
- try smaller inputs to make the problem smaller
- base condition is needed to stop the recursion, otherwise infinite loop will occur


#### example of a Russian doll
```
def openRussianDoll(doll):
	if doll == 1:
		print("All dolls are opened")
	else:
		openRussianDoll(doll-1)
```



## Why Recursion?

- important in programming, and it helps you break down big problems into smaller ones 
- sometimes better than iterative approach 
- when to use? If you can divide the problem in similar subproblems then you can use recursion
- Prominent use is in ds like trees and graphs
- interviews
- used in many algos, like divide and conquer, greedy and dynamic programming


## How Recursion works

- a method calls it self
- exit from infinite loop

basic syntax
```
def recursionMethod(params):
	if exit from condition satisfied:
		return some value
	else:
		recursionMethod(modified params)
```

![[Pasted image 20240716135222.png]]