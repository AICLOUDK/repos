# repos
models.py
Purpose: Defines the data models (database schemas) for your application.
What it contains: Classes that inherit from django.db.models.Model, representing database tables.
Example:
CopyRun
from django.db import models

class Product(models.Model):
    name = models.CharField(max_length=100)
    price = models.DecimalField(max_digits=8, decimal_places=2)
    description = models.TextField()

    def __str__(self):
        return self.name
Role: When you run migrations, Django creates the corresponding tables in the database based on these models.
admin.py
Purpose: Configures how models are displayed and managed in the Django admin interface.
What it contains: Registration of models with the admin site, sometimes with customizations.
Example:
CopyRun
from django.contrib import admin
from .models import Product

@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    list_display = ('name', 'price')
    search_fields = ('name',)
Role: Enables you to add, edit, delete, and view data entries for your models via Django's built-in admin panel.
Summary
models.py: Defines the database structure (data models).
admin.py: Customizes how those models are managed and viewed in the admin interface.
