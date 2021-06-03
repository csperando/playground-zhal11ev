# What is recursion

One of the most common tutorials for learning recursive algorithms is to calculate the factorial of some integer n. 

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
