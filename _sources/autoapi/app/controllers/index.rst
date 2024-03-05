:py:mod:`app.controllers`
=========================

.. py:module:: app.controllers

.. autoapi-nested-parse::

   Module for controllers exports



Submodules
----------
.. toctree::
   :titlesonly:
   :maxdepth: 1

   products/index.rst


Package Contents
----------------

.. py:data:: products_controller

   Endpoint to save a new product.

   This endpoint requires authentication and an admin role. It accepts JSON data representing a product,
   validates the necessary fields, creates a Product instance, and saves it to the database.

   Request Method: POST
   Authentication: Required
   Required Roles: ADMIN_ROLE

