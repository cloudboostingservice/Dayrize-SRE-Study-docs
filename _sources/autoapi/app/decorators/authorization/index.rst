:py:mod:`app.decorators.authorization`
======================================

.. py:module:: app.decorators.authorization

.. autoapi-nested-parse::

   Module: Role-based Access Control
   ==================================

   This module provides a class-based decorator, `RequiredRoles`, for enforcing role-based access control (RBAC) on Flask routes. The decorator validates JWT tokens to ensure that the requestor has the required roles to access the protected resource. It leverages the JWT's claims to check the user's roles against the roles required for accessing the resource. If the user does not have the required roles, or if there's an issue with parsing the token, an `AuthError` is raised, restricting access to the resource. This approach allows for fine-grained access control based on user roles, enhancing the security and flexibility of application access management.

   Classes:
   - `RequiredRoles`: Decorator class for checking user roles against required roles for accessing a resource.

   Functions:
   - `is_authorized(roles, user_roles)`: Helper function to determine if the user has any of the required roles.

   Exceptions:
   - `AuthError`: Raised when a user does not have the necessary roles or there is an issue with the token.
   - `CustomError`: Raised when an unexpected error occurs.



Module Contents
---------------

Classes
~~~~~~~

.. autoapisummary::

   app.decorators.authorization.RequiredRoles



Functions
~~~~~~~~~

.. autoapisummary::

   app.decorators.authorization.is_authorized



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



.. py:function:: is_authorized(roles, user_roles)

   Determines if the user has any of the specified roles.

   :param roles: The list of roles required to access a resource.
   :type roles: list
   :param user_roles: The list of roles assigned to the user.
   :type user_roles: list

   :returns: True if the user has at least one of the required roles, False otherwise.
   :rtype: bool


