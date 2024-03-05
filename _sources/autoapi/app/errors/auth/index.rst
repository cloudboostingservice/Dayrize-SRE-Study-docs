:py:mod:`app.errors.auth`
=========================

.. py:module:: app.errors.auth

.. autoapi-nested-parse::

   Module: Authentication Error Handling
   =====================================

   This module defines the AuthError class for handling authentication-related exceptions within the application. It provides detailed information on authentication failures, including specific error messages and HTTP status codes, facilitating clear and actionable error reporting.

   Classes:
   - AuthError: Exception class for authentication errors.

   Exceptions:
   - AuthError: Raised to signal an authentication error, equipped with error details and an HTTP status code.



Module Contents
---------------

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



