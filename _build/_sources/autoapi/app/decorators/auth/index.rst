:py:mod:`app.decorators.auth`
=============================

.. py:module:: app.decorators.auth

.. autoapi-nested-parse::

   Module: Authentication Decorator
   ===============================

   This module provides a decorator function, `requires_auth`, which is used to secure Flask routes by validating JWT tokens. The validation process involves decoding the JWT token using a public key obtained from Auth0's JWKS endpoint, ensuring the token is authentic, not expired, and has the appropriate permissions for accessing the requested resources. If the validation fails due to issues like expired tokens, invalid claims, or incorrect signature, an `AuthError` with a descriptive message and a 401 status code is raised. This mechanism ensures that only authenticated and authorized requests are processed by the protected endpoints.

   Functions:
   - `requires_auth(f)`: A decorator function to enforce authentication on Flask routes.

   Exceptions:
   - `AuthError`: Custom exception used to handle authentication and authorization errors.



Module Contents
---------------


Functions
~~~~~~~~~

.. autoapisummary::

   app.decorators.auth.requires_auth



.. py:function:: requires_auth(f)

   Decorator that checks if the request has a valid JWT access token.

   It retrieves the token from the request's headers, decodes, and validates it using the public key from Auth0's JWKS (JSON Web Key Set). It ensures the token is valid, not expired, and contains the correct audience and issuer.

   :param f: The wrapped function that requires authentication.
   :type f: function

   :returns: The decorated function which will only be executed if the token is valid.
   :rtype: function

   :raises AuthError: If the token is expired, has invalid claims, cannot be parsed, or is otherwise invalid, an AuthError is raised with a 401 status code.

   .. rubric:: Examples

   @app.route('/private')
   @requires_auth
   def private_route():
       return "Secret data"


