# What is Recursion?

Recursion is the term used for algorithms that solve for a value in a sequence that depends on other values in the same sequence. 

One of the most common tutorials for learning recursive algorithms is to calculate the factorial of some integer n, denoted n! The formula can be expressed as follows:

+ N! = N * (N-1) * (N-2) * ... * 2 * 1

For example: 
+ 5! = 5 * 4 * 3 * 2 * 1 = 120 
+ 4! = 4 * 3 * 2 * 1 = 24 
+ 3! = 3 * 2 * 1 = 6 


```python runnable
def factorial(n):
    if(n > 1):
        return n*factorial(n-1)
    else:
        return n

print(factorial(4))
```

# Advanced usage

If you want a more complex example (external libraries, viewers...), use the [Advanced Python template](https://tech.io/select-repo/429)
