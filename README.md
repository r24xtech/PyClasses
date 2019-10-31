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


Python Crash Course, 2nd Edition.pdf
