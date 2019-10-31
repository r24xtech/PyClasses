# PyClasses
Dealing with Classes in Python - Object-oriented programming

Key points:
* Making an object from a class is called instantiation, and you work with instances of a class.
* By convention, capitalized names refer to classes in Python.
* A function that’s part of a class is a method.

```python
class Dog:
	def __init__(self, name, age):
		self.name = name
		self.age = age

	def sit(self):
		print(f"{self.name} is now sitting.")

	def roll_over(self):
		print(f"{self.name} rolled over!")
```

* The `__init__()` method is a special method that Python runs automatically whenever we create a new instance based on the Dog class.
* The self parameter is required in the method definition, and it must come first before the other parameters. It must be included in the definition because when Python calls this method later (to create an instance of Dog), the method call will automatically pass the self argument. 
* Every method call associated with an instance automatically passes self, which is a reference to the instance itself; it gives the individual instance access to the attributes and methods in the class. When we make an instance of Dog, Python will call the `__init__()` method from the Dog class.
* The line `self.name = name` takes the value associated with the parameter name and assigns it to the variable name, which is then attached to the instance being created. The same process happens with `self.age = age`. Variables that are accessible through instances like this are called **attributes**.
```python
my_dog = Dog('Willie', 6)

print(f"My dog's name is {my_dog.name}.")
print(f"My dog is {my_dog.age} years old.")
## Calling mmethods
my_dog.sit()
my_dog.roll_over()
```


Python Crash Course, 2nd Edition.pdf
