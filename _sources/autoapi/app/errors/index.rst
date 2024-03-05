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

   Custom error class with bad request (400) default status code

   .. py:attribute:: status_code
      :value: 400

      

   .. py:method:: to_dict()

      Error to dict function



.. py:exception:: AuthError(error, status_code)


   Bases: :py:obj:`Exception`

   Auth error class


