:py:mod:`jwt`
=============

.. py:module:: jwt

.. autoapi-nested-parse::

   Utils - JWT
   ================

   This module provides utilities for handling JWT (JSON Web Tokens) authentication
   within a Flask application. It includes functions to extract and validate JWTs from
   authorization headers in requests.

   Functions:
       get_token_auth_header() -> str: Extracts the JWT from the Authorization header of
       the incoming request.

   Constants:
       AUTH0_DOMAIN (str): The Auth0 domain, fetched from environment variables.
       CLIENT_ID (str): The Auth0 Client ID, fetched from environment variables.
       ALGORITHMS (list): List of algorithms used for decoding JWTs, defaulting to RS256.

   Exceptions:
       AuthError: Raised when the Authorization header is missing, not properly formatted, or does not start with 'Bearer '. Includes an error code, a descriptive message, and sets the HTTP status code to 401.



Module Contents
---------------


Functions
~~~~~~~~~

.. autoapisummary::

   jwt.get_token_auth_header



Attributes
~~~~~~~~~~

.. autoapisummary::

   jwt.AUTH0_DOMAIN
   jwt.CLIENT_ID
   jwt.ALGORITHMS


.. py:data:: AUTH0_DOMAIN

   

.. py:data:: CLIENT_ID

   

.. py:data:: ALGORITHMS
   :value: ['RS256']

   

.. py:function:: get_token_auth_header()

   Obtains the Access Token from the Authorization Header.

   This function extracts the JWT token from the Authorization header in the request.
   It validates the structure of the header and the presence of the token. If the header
   is not present, or the token is in an incorrect format, an AuthError is raised.

   :returns: The extracted JWT token.
   :rtype: str

   :raises AuthError: If the Authorization header is missing, not started with 'Bearer ',
       the token is not found, or the header format is incorrect.


