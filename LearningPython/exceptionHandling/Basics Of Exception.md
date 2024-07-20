
## Understanding exceptions

It is an error that occurs during the execution of a program. When an error occurs in Python, it generates an exception which can be handled to prevent the program from crashing


### Common Exceptions

- ZeroDivisionError : when divided by zero
- IndexError: Accessing an invalid index in a list
- KeyError: Accessing a non-existent key in a dictionary
- FileNotFoundError: file operations fails


### Basics of Exception Handling

Python uses 'try' , 'except' , 'else' and 'finally' blocks to handle the exceptions


syntax:
```

try:
	#code that might raise an exception
except ExceptionType:
	#code to handle the exception
	
```

```
try:
	x = 1/0
except ZeroDivisionError:
	print("You cant divide by zero")
```


#### **Handling Multiple Exceptions**

You can handle multiple exceptions by specifying multiple except blocks

```
try:
	value = int(input('enter a number'))
	result = 10/value
except ValueError:
	print('Thats not a valid number')
except ZeroDivisionError:
	print('Cant divide by zero')
```


#### **Finally**

The finally block will execute no matter what whether the exception occured or not.
Typically used for cleanup actions

```
try:
	file = open('example.txt','r')
	content = file.read()
except FileNotFoundError:
	print("file not found")
finally:
	file.close()
	print("file Closed")
```


#### **Raising exceptions**

You can raise exceptions using the 'raise' keyword. This is useful if you want to trigger an exception manually

```
def divide(a,b):
	if b == 0:
		raise ValueError("Cannot divide by Zero")
	return a/b
	
try:
	divide(10,0)
except ValueError as e:
	print(e)
```

### Best Practices

- Catch specific exceptions rather than using a bare `except` clause.
- Avoid catching all exceptions with `except Exception:` unless you have a good reason.
- Always clean up resources, like files or network connections, using `finally`.
- Use custom exceptions to provide more meaningful error messages and handle them appropriately.


### Are exception and error the same?

In python, these two are related concepts but not exactly the same.

Error refers to the issues in a program that prevent it from executing correctly,
typically result of syntax mistakes or problems that cant be handled by the program during exception

Exceptions are subset of runtime errors. They are the event that disrupt the normal flow of problem but can be handled by using try-except blocks.
