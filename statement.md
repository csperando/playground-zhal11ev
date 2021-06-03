# What is Recursion?

In a very basic sense, you can think of recursion as a term used to describe algorithms that solve for a value in a sequence that depends on other values in the same sequence. 

One of the most common tutorials for learning recursive algorithms is to calculate the factorial of some integer n, denoted n! The formula can be expressed as follows:

> N! = N * (N-1) * (N-2) * ... * 2 * 1

For example: 
+ 5! = 5 * 4 * 3 * 2 * 1 = 120 
+ 4! = 4 * 3 * 2 * 1 = 24 
+ 3! = 3 * 2 * 1 = 6 

Below is a recursive function that calculates N! Given some input value n, the function will return a call to itself until the condition in the if-statement is not met.
This works because the arguement of the function being called is changed every time in such a way that eventually n <= 1. 

```python runnable
def factorial(n):
    if(n > 1):
        return n*factorial(n-1)
    else:
        return n

print("6! =", factorial(4))
```

# Advanced usage

If you want a more complex example (external libraries, viewers...), use the [Advanced Python template](https://tech.io/select-repo/429)
