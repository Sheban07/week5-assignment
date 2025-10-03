# Assignment 1: Design Your Own Class

# Base Class
class Device:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model
    
    def device_info(self):
        return f"Device: {self.brand} {self.model}"

# Derived Class (Inheritance from Device)
class Smartphone(Device):
    def __init__(self, brand, model, storage, battery):
        super().__init__(brand, model)   # Inherit from Device
        self.__storage = storage         # Encapsulation (private attribute)
        self.battery = battery
    
    # Method to simulate making a call
    def make_call(self, number):
        return f"Calling {number}..."

    # Getter for storage (encapsulation)
    def get_storage(self):
        return f"Storage: {self.__storage} GB"

    # Setter for storage
    def set_storage(self, new_storage):
        self.__storage = new_storage

# Creating objects
phone1 = Smartphone("Samsung", "S24 Ultra", 256, "5000mAh")
phone2 = Smartphone("Apple", "iPhone 15", 128, "4200mAh")

print(phone1.device_info())
print(phone1.make_call("0723456789"))
print(phone1.get_storage())

# Update storage
phone1.set_storage(512)
print(phone1.get_storage())

# Activity 2: Polymorphism Challenge
class Animal:
    def move(self):
        pass  # To be overridden by child classes

class Dog(Animal):
    def move(self):
        return "Running 🐕"

class Bird(Animal):
    def move(self):
        return "Flying 🕊️"

class Fish(Animal):
    def move(self):
        return "Swimming 🐠"

# Polymorphism in action
animals = [Dog(), Bird(), Fish()]

for animal in animals:
    print(animal.move())

