:py:mod:`app.errors.custom`
===========================

.. py:module:: app.errors.custom

.. autoapi-nested-parse::

   Custom Error module for internal application Errors



Module Contents
---------------

.. py:exception:: CustomError(message, status_code=None, payload=None)


   Bases: :py:obj:`Exception`

   Custom error class with bad request (400) default status code

   .. py:attribute:: status_code
      :value: 400

      

   .. py:method:: to_dict()

      Error to dict function



