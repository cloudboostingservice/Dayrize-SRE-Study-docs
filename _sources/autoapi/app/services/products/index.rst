:py:mod:`app.services.products`
===============================

.. py:module:: app.services.products

.. autoapi-nested-parse::

   Services - Products
   ======================

   This module encapsulates the core functionality for managing product information within a database, providing essential operations such as creating, retrieving a single product by its ID, and listing all products. It interfaces with a Firestore database to persist product data, ensuring data consistency and integrity across product management tasks.

   Functions:
       save_product(product: Product):
           Saves a product instance to the database. This function accepts a product object, transforms it into a dictionary format, and stores it in the Firestore database under the 'products' collection with a document ID matching the product's unique ID.

       get_products() -> list:
           Fetches a comprehensive list of all products stored in the database. It retrieves each product document from the 'products' collection, converts the documents into dictionary format, and returns a list of these dictionaries, effectively providing a snapshot of all available products.

       get_product(product_id: str) -> dict or None:
           Searches for and retrieves a single product by its unique identifier (ID). If the product exists within the 'products' collection, its document is converted to a dictionary and returned. If no product matches the provided ID, the function returns None, indicating the absence of the product.
   Exceptions:
       FirestoreError: An error that occurs during the interaction with the Firestore database, such as issues with reading from or writing to the database.



Module Contents
---------------


Functions
~~~~~~~~~

.. autoapisummary::

   app.services.products.save_product
   app.services.products.get_products
   app.services.products.get_product
   app.services.products.add_review



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


.. py:function:: add_review(review: app.model.review.Review, product_id)

   Saves a product's review to the database.

   This function takes a review instance, converts it to a dictionary, and saves it to the Firestore database.
   Each review is saved in the product's document corresponding to its unique ID within the 'products' collection.

   :param review: The review instance to be saved.
   :type review: Review
   :param product_id: The id of the product


