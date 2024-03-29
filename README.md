# PyClasses
Dealing with Classes in Python - Object-oriented programming <br>
Python Crash Course, 2nd Edition

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
<hr><hr>

```python
class Car:
	def __init__(self, make, model, year):
		self.make = make
		self.model = model
		self.year = year
		self.odometer_reading = 0

	def get_descriptive_name(self):
		long_name = f"{self.year} {self.make} {self.model}"
		return long_name.title()

	def read_odometer(self):
		print(f"This car has {self.odometer_reading} miles on it.")

my_new_car = Car('audi', 'a4', 2019)
print(my_new_car.get_descriptive_name())
my_new_car.read_odometer()
```
Modifying Attribute Values
1. change the value directly through an instance `my_new_car.odometer_reading = 23`
2. set the value through a method
3. increment the value (add a certain amount to it) through a method.
```python
## (2)
def update_odometer(self, mileage):
	self.odometer_reading = mileage
my_new_car.update_odometer(23)
```
<hr><hr>

**Inheritance**
* The child class can inherit any or all of the attributes and methods of its parent class, but it’s also free to define new attributes and methods of its own.
* The name of the par-ent class must be included in parentheses in the definition of a child class.
* The super() function is a special function that allows you to call a method from the parent class. 
```python
class ElectricCar(Car):
	def __init__(self, make, model, year):
		super().__init__(make, model, year)


my_tesla = ElectricCar('tesla', 'model s', 2019)
print(my_tesla.get_descriptive_name())
```
=> Defining Attributes and Methods for the Child Class
```python
class ElectricCar(Car):

	def __init__(self, make, model, year):
		super().__init__(make, model, year)
		self.battery_size = 75

	def describe_battery(self):
		print(f"This car has a {self.battery_size}-kWh battery.")


my_tesla = ElectricCar('tesla', 'model s', 2019)
print(my_tesla.get_descriptive_name())
my_tesla.describe_battery()
```
=> Instances as Attributes
```python
class Battery:
	def __init__(self, battery_size=75):
		self.battery_size = battery_size

	def describe_battery(self):
		print(f"This car has a {self.battery_size}-kWh battery.")

class ElectricCar(Car):

	def __init__(self, make, model, year):
		super().__init__(make, model, year)
		self.battery = Battery()

	def describe_battery(self):
		print(f"This car has a {self.battery_size}-kWh battery.")


my_tesla = ElectricCar('tesla', 'model s', 2019)
print(my_tesla.get_descriptive_name())
my_tesla.battery.describe_battery()
```
