```Python

def common():
    """A common function. Can be any function in your code."""
    print("I'm a normal function that print a message.")

def decorator_function(function):
    """A decorator function: It return a wrapper function that encapsulate your function, and allow to modify its behavior"""

    def wrapper():
        print("I'm a decorator function, I can do something before")
        function()
        print("I'm a decorator function, I can do something after")
    
    # Return the function Object. We don't call it !
    return wrapper


```
