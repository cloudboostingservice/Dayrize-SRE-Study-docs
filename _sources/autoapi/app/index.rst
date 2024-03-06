:py:mod:`app`
=============

.. py:module:: app

.. autoapi-nested-parse::

   Main Module
   <<<<<<< Updated upstream
   ===========

   This module sets up and configures the Flask application for the Dayrize Site Reliability Engineering Case Study. It integrates with Auth0 for authentication, utilizes Flask-Loguru for logging, and handles custom errors through defined error handlers. The application supports routes for product management, user authentication (login and logout), and the processing of authentication callbacks.

   Functions:
       create_app() -> Flask: Creates and configures the Flask application instance.
           - It sets up logging, registers the products controller and auth controller blueprints, and defines routes for authentication and error handling. Environment variables are used for configuration.
           - Inner Functions:
               - invalid_api_usage(e: CustomError) -> tuple: Handles custom errors defined in the application, returning a JSON response with the error details and HTTP status code.
               - handle_auth_error(ex: AuthError) -> Response: Handles authentication errors, returning a JSON response with the authentication error details and HTTP status code.

   Constants:
       ENV_FILE (str): Path to the environment variables file, found using `find_dotenv`.

   =======
   ======================
   This module sets up and configures the Flask application for the Dayrize Site Reliability Engineering Case Study. It integrates with external services like Auth0 for authentication, utilizes Flask-Loguru for advanced logging capabilities, and handles custom errors through well-defined error handlers. Specifically, it supports routes for product management, user authentication processes (including login and logout functionalities), and the processing of authentication callbacks efficiently.

   Functions:
   create_app() -> Flask: Creates and configures the Flask application instance, setting up logging, registering controller blueprints for product management and authentication routes, and defining error handlers for custom and authentication-related errors.

   Constants:
   ENV_FILE (str): Path to the .env file, determined by searching the directory structure. Used to load environment variables critical for application configuration.
   Exceptions:
       CustomError: A custom exception class for handling application-specific errors. It allows for structured error responses that include a status code and a detailed error message.
       AuthError: An exception class designed for handling authentication-related errors. It is used to construct responses with specific error information and the corresponding HTTP status code when authentication fails.
   >>>>>>> Stashed changes



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
   app.auth_controller
   app.ENV_FILE


.. py:data:: products_controller

   

.. py:data:: auth_controller

   

.. py:exception:: CustomError(message, status_code=None, payload=None)


   Bases: :py:obj:`Exception`

   CustomError exception for handling various application errors with flexibility in status codes and additional payload.

   .. attribute:: message

      The error message describing what went wrong.

      :type: str

   .. attribute:: status_code

      HTTP status code to be returned. Defaults to 400 (Bad Request).

      :type: int

   .. attribute:: payload

      Additional data to be included in the error response.

      :type: dict, optional

   .. method:: _init_(self, message, status_code=None, payload=None):

      Initializes the CustomError with a message, an optional status code, and an optional payload.

   .. method:: to_dict(self):

      Converts the error details into a dictionary for JSON serialization.


   .. rubric:: Examples

   raise CustomError('An unexpected error occurred', status_code=500, payload={'detail': 'More info'})

   .. py:attribute:: status_code
      :value: 400

      

   .. py:method:: to_dict()

      Serializes the error information into a dictionary format.

      :returns: The error details including the message and any additional payload.
      :rtype: dict



.. py:exception:: AuthError(error, status_code)


   Bases: :py:obj:`Exception`

   AuthError exception for handling authentication errors with detailed information.

   .. attribute:: error

      Description of the error that occurred.

      :type: str

   .. attribute:: status_code

      HTTP status code associated with the error.

      :type: int

   .. method:: _init_(self, error, status_code):

      Initializes the AuthError with an error message and a status code.



.. py:data:: ENV_FILE

   

.. py:function:: create_app()

   Creates and configures the Flask application.

   Sets up logging based on environment variables, registers the products controller blueprint for managing product-related routes,
   and defines routes for authentication and error handling. Utilizes environment variables for configuration such as
   LOG_LEVEL, AUTH0_DOMAIN, and AUTH0_CLIENT_ID for integration with external services.

   :return: The Flask application instance.


