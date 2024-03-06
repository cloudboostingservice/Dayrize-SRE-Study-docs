:py:mod:`app.errors.custom`
===========================

.. py:module:: app.errors.custom

.. autoapi-nested-parse::

   Errors - Custom Error Handling
   =========================================

   This module introduces the CustomError class to manage a wide range of application errors beyond authentication issues. It allows for specifying error messages, HTTP status codes, and additional payload for a rich error reporting experience. The CustomError class enhances the application's ability to communicate errors clearly and effectively.

   Classes:
   - CustomError: Exception class for custom application errors.

   Exceptions:
   - CustomError: Used to indicate various application-specific errors, supporting custom status codes and additional error details.



Module Contents
---------------

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



