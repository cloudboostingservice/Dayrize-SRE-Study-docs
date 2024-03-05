:py:mod:`app.errors`
====================

.. py:module:: app.errors

.. autoapi-nested-parse::

   Module declaration for Errors export



Submodules
----------
.. toctree::
   :titlesonly:
   :maxdepth: 1

   auth/index.rst
   custom/index.rst


Package Contents
----------------

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



