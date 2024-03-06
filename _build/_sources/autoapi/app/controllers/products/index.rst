:py:mod:`app.controllers.products`
==================================

.. py:module:: app.controllers.products

.. autoapi-nested-parse::

   products_controller Module
   ==========================

   This module defines the Flask Blueprint for product management endpoints in a Flask application.
   It includes endpoints for saving a new product, retrieving all products, and getting a single product by ID.
   These endpoints incorporate authentication and role-based access control.

   Endpoints:
       POST /api/products/ : Saves a new product to the database.
       GET /api/products/ : Retrieves all products from the database.
       GET /api/products/<product_id> : Retrieves a single product by its unique ID from the database.

   Functions:
       save_product(): Endpoint for saving a new product, requiring authentication and admin role.
       get_products(): Endpoint for retrieving all products.
       get_product(product_id): Endpoint for retrieving a single product by ID.
       validate_product_fields(product): Validates the required fields in a product's data.



Module Contents
---------------


Functions
~~~~~~~~~

.. autoapisummary::

   app.controllers.products.save_product
   app.controllers.products.get_products
   app.controllers.products.get_product
   app.controllers.products.validate_product_fields



Attributes
~~~~~~~~~~

.. autoapisummary::

   app.controllers.products.products_controller


.. py:data:: products_controller

   

.. py:function:: save_product()

   Endpoint to save a new product.

   This endpoint requires authentication and an admin role. It accepts JSON data representing a product,
   validates the necessary fields, creates a Product instance, and saves it to the database.

   Request Method: POST
   Authentication: Required
   Required Roles: ADMIN_ROLE


.. py:function:: get_products()

   Endpoint to retrieve all products.

   This endpoint fetches all products from the database and returns them as a JSON list.

   Request Method: GET
   Authentication: Not Required


.. py:function:: get_product(product_id)

   Endpoint to retrieve a single product by its unique ID.

   If the product is found, it returns the product data as JSON. If not found, it raises a CustomError.

   Request Method: GET
   Authentication: Not Required
   :param product_id: The unique ID of the product to retrieve.
   :type product_id: str


.. py:function:: validate_product_fields(product)

   Validates the required fields in a product's data.

   This function checks if the 'name' and 'description' fields are present in the product data. If not,
   it raises a CustomError.

   :param product: The product data to validate.
   :type product: dict


