
### Types of Orders of Growth

- Constant : when the time doesn't increase regardless of the increase in input. Considered best.
- Linear: When input increases the time increases as well. Is considered okay and well
- Quadratic: When the input is increased once, the time is increased with the power of 2, not considered good. Eg: Nested loops
- Logarithmic: when input is increased by 10 then output is increased by 1. Input is multiplied, but the time is added. Is considered 2nd best after constant
- nLogn: worse than linear but better than quadratic
- exponential: worst, when input is getting increased by 1, the time is getting multiplied. Just opposite than log


### Complexity Growth
![[Pasted image 20240720183008.png]]
The above is better, lower ones are worse.




## Questions

**Tell the complexity**


Problem 1:
```
L = [1,2,3,4,5]
sum = 0 
for i in L:
	sum+=i
print(sum)

product = 1
for i in L:
	product *= i 
print(product)
```

Answers:
we can see there are two loops not nested but independent. each runs till the length of the array. So the complexity of each loop is O(n)
But there are two of it, which makes it O(2n), but the multiplication constants are not considered so : O(n)