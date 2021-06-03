# What is Recursion?

In a very basic sense, you can think of recursion as a term used to describe algorithms that solve for a value in a sequence that depends on other values in the same sequence. 

One of the most common tutorials for learning recursive algorithms is to calculate the factorial of some integer n, denoted n! The formula can be expressed as follows:

> N! = N * (N-1) * (N-2) * ... * 2 * 1

For example: 
+ 5! = 5 * 4 * 3 * 2 * 1 = 120 
+ 4! = 4 * 3 * 2 * 1 = 24 
+ 3! = 3 * 2 * 1 = 6 

Below is a recursive function that calculates N! Given some input value n, the function will return a call to itself until the condition in the if-statement is false.

```python runnable
def factorial(n):
    if(n > 1):
        return n*factorial(n-1)
    else:
        return n

print("6! =", factorial(6))
```

If you have not worked with this type of algorithm before, then it can be a little counter-intuitive for most top-down programming mindsets. So lets break it down a little further.

In the example above, we want to calculate 6! so we call factorial(6)
Since n = 6 and 6 > 1, we return n * factorial(5) on line 3. However, we do not return/exit the function at this point, because we still need to evaluate factorial(5).
So the cycle repeats for n = 5, then n = 4 ... n = 2 and finally n = 1. 

> return 6 * factorial(5)
>> return 5 * factorial(4)
>>> return 4 * facorial(3)
>>>> return 3 * factorial(2)
>>>>> return 2 * factorial(1)
>>>>>> return 1

At this point we have hit the maximum recursion depth of the algorithm. factorial(1) evaluates to 1 and factorial(2) returns 2 * 1. Then factorial(3) returns 3 * 2, factorial(4) returns 4 * 6, and on until our initial function call factorial(6) returns 720.

The order of execution is extremely important when designing a recursion algorithm. Often times the value you are interested in finding is at the bottom depth of your function calls, with half of your calculations remaining. Just because something is returned from a function in a recursion algorithm does not mean you will see that result like you would in a more linear top-down program.

# Infinite Loops

In the above code, the function will call itself until the parameter n is less than or equal to one. Also, every time it is called recursively, the input parameter n is decremented by 1.
This prevents the function from calling itself endlessly over and over again. For more complex examples, make sure the value you are interested in calculating is well-defined and will not lead to an infinite recursion depth.

## Limit the Depth of your Calculations

Depending on the problem you are trying to solve, it may be a good idea to limit the depth of your recursive function. For more advanced algorithms such as Monte Carlo Tree Search (MCTS) used in chess programs, it is unreasonable to try to calculate every possible move. However, if you only want to look 3 or so steps ahead then you need to keep track of the "depth" of your algorithm.

Below is a snippet of an almost identical factorial function to the one above. However, this one keeps track of how many times the factorial function has called itself. If it calls itself 7 times or more, then it will print an error message and return 0.

```python runnable
def factorial(n, depth):
    if(depth < 7):
        if(n > 1):
            return n*factorial(n-1, depth + 1)
        else:
            return n
    else:
        print("ERROR: maximum recursion depth exceeded.")
        return 0


print("6! =", factorial(6, 0))
print("8! =", factorial(8, 0))
```


### Additional Resources

[Recursion Wikipedia](https://en.wikipedia.org/wiki/Recursion_(computer_science))

