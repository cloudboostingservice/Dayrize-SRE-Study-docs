:py:mod:`app.services.products`
===============================

.. py:module:: app.services.products

.. autoapi-nested-parse::

   product_service Module
   ======================

   This module contains the core logic for managing product data within a database.
   It provides functions to save, retrieve a single product by ID, and list all products.

   Functions:
       save_product(product: Product): Saves a product instance to the database.
       get_products() -> list: Retrieves a list of all products from the database.
       get_product(product_id: str) -> dict or None: Retrieves a single product by its unique ID.

   Dependencies:
       db (Firestore Database): An instance of the Firestore database from the app's configuration.
       Product (class): The Product model class used for type annotation of product instances.



Module Contents
---------------


Functions
~~~~~~~~~

.. autoapisummary::

   app.services.products.save_product
   app.services.products.get_products
   app.services.products.get_product



.. py:function:: save_product(product: app.model.Product)

   Saves a product to the database.

   This function takes a product instance, converts it to a dictionary, and saves it to the Firestore database.
   Each product is saved in a document corresponding to its unique ID within the 'products' collection.

   :param product: The product instance to be saved.
   :type product: Product


.. py:function:: get_products()

   Retrieves all products from the database.

   This function fetches all product documents from the 'products' collection, converts each document to a dictionary,
   and returns a list of these dictionaries representing all products.

   :returns: A list of dictionaries, each representing a product.
   :rtype: list


.. py:function:: get_product(product_id)

   Retrieves a product by its unique ID.

   This function looks up a single product in the 'products' collection by its document ID. If found,
   the document is converted to a dictionary and returned. If no product is found with the given ID,
   None is returned.

   :param product_id: The unique ID of the product to retrieve.
   :type product_id: str

   :returns: A dictionary representing the found product, or None if no product is found.
   :rtype: dict or None


