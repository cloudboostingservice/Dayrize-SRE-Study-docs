:py:mod:`app.decorators`
========================

.. py:module:: app.decorators

.. autoapi-nested-parse::

   Module declaration for decorators export



Submodules
----------
.. toctree::
   :titlesonly:
   :maxdepth: 1

   auth/index.rst
   authorization/index.rst


Package Contents
----------------

Classes
~~~~~~~

.. autoapisummary::

   app.decorators.RequiredRoles



Functions
~~~~~~~~~

.. autoapisummary::

   app.decorators.requires_auth



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


.. py:class:: RequiredRoles(roles)


   A decorator for enforcing role-based access control on Flask routes.

   .. attribute:: roles

      A list of roles required to access the resource.

      :type: list

   .. method:: __call__(self, f):

      Decorates a Flask route to require certain roles for access.


   .. rubric:: Examples

   @app.route('/admin')
   @RequiredRoles(['admin'])
   def admin_route():
       return "Admin data"

   .. py:method:: __call__(f)

      Decorator method that checks if the user has any of the required roles.

      :param f: The Flask route function to decorate.
      :type f: function

      :returns: The decorated function with role-based access control.
      :rtype: function

      :raises CustomError: If no roles are specified for the decorator.
      :raises AuthError: If the user does not have the required roles or there's an error with token parsing.



