---
layout: post
title:  Factory method in python
published: true
category: Python
---

Factory method

 

We may not always know what kind of objects we want to create in advance.
Some objects can be created only at execution time after a user requests so.

``` python
class Car(object):
 
    def factory(type):
        if type == "Racecar": 
            return Racecar()
        if type == "Van": 
            return Van()
        assert 0, "Bad car creation: " + type
 
    factory = staticmethod(factory)
 
class Racecar(Car):
    def drive(self): print("Racecar driving.")
 
class Van(Car):
    def drive(self): print("Van driving.")
 
# Create object using factory.
obj = Car.factory("Racecar")
obj.drive()

```
Output:

Racecar driving.

Source:https://pythonspot.com/factory-method/
