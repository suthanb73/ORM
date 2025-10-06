# Ex02 Django ORM Web Application
# Date:06/10/25
# AIM
To develop a Django application to store and retrieve data from a bank loan database using Object Relational Mapping(ORM).

# ENTITY RELATIONSHIP DIAGRAM
## DESIGN STEPS
## STEP 1:
Clone the problem from GitHub

## STEP 2:
Create a new app in Django project

## STEP 3:
Enter the code for admin.py and models.py

## STEP 4:
Execute Django admin and create details for 10 books

# PROGRAM

models.py
from django.db import models
from django.contrib import admin

class Car(models.Model):
    car_id = models.AutoField(primary_key=True)  # Primary Key
    brand = models.CharField(max_length=50, help_text="Brand of the car")
    model = models.CharField(max_length=50, help_text="Model of the car")
    year = models.IntegerField(help_text="Manufacturing year of the car")
    price = models.DecimalField(max_digits=10, decimal_places=2, help_text="Price of the car")
    fuel_type = models.CharField(max_length=20, choices=[('Petrol', 'Petrol'), ('Diesel', 'Diesel'), ('Electric', 'Electric'), ('CNG', 'CNG')], help_text="Fuel type of the car")

    def _str_(self):
        return f"{self.brand} {self.model} ({self.year})"

class CarAdmin(admin.ModelAdmin):
    list_display = ('brand', 'model', 'year', 'price', 'fuel_type')
admin.site.register(Car, CarAdmin)

admin.py
from django.contrib import admin
from .models import Car, CarAdmin

# OUTPUT
<img width="1895" height="913" alt="Screenshot 2025-09-21 105023" src="https://github.com/user-attachments/assets/8f0d057e-ac43-4817-8522-fffe3bcf9fd7" />

# RESULT
Thus the program for creating a database using ORM hass been executed successfully
