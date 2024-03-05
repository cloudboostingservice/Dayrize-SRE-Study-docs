:py:mod:`app`
=============

.. py:module:: app

.. autoapi-nested-parse::

   Main Module
   ===========

   This module sets up and configures the Flask application for the Dayrize Site Reliability Engineering Case Study.
   It integrates with Auth0 for authentication, utilizes Flask-Loguru for logging, and handles custom errors through
   defined error handlers. The application supports routes for product management, user authentication (login and logout),
   and the processing of authentication callbacks.

   Functions:
       create_app(): Creates and configures the Flask application instance.



Subpackages
-----------
.. toctree::
   :titlesonly:
   :maxdepth: 3

   config/index.rst
   controllers/index.rst
   decorators/index.rst
   errors/index.rst
   model/index.rst
   services/index.rst


Package Contents
----------------


Functions
~~~~~~~~~

.. autoapisummary::

   app.create_app



Attributes
~~~~~~~~~~

.. autoapisummary::

   app.products_controller
   app.ENV_FILE


.. py:data:: products_controller

   Endpoint to save a new product.

   This endpoint requires authentication and an admin role. It accepts JSON data representing a product,
   validates the necessary fields, creates a Product instance, and saves it to the database.

   Request Method: POST
   Authentication: Required
   Required Roles: ADMIN_ROLE

.. py:exception:: CustomError(message, status_code=None, payload=None)


   Bases: :py:obj:`Exception`

   Custom error class with bad request (400) default status code

   .. py:attribute:: status_code
      :value: 400

      

   .. py:method:: to_dict()

      Error to dict function



.. py:exception:: AuthError(error, status_code)


   Bases: :py:obj:`Exception`

   Auth error class


.. py:data:: ENV_FILE

   

.. py:function:: create_app()

   Creates and configures the Flask application.

   Sets up logging based on environment variables, registers the products controller blueprint for managing product-related routes,
   and defines routes for authentication and error handling. Utilizes environment variables for configuration such as
   LOG_LEVEL, AUTH0_DOMAIN, and AUTH0_CLIENT_ID for integration with external services.

   :return: The Flask application instance.


