:py:mod:`app.model.review`
==========================

.. py:module:: app.model.review

.. autoapi-nested-parse::

   Model - Review
   ==============

   .. module:: review
      :synopsis: This module contains the Review class.

   Review Class
   -------------

   .. class:: Review(description, rating)

      Implements a review with a name and a description.

      .. py:attribute:: _id

         A unique identifier for the review. Automatically generated upon instantiation.

      .. py:method:: __init__(description: str, rating: float)

         Initializes a new instance of the Review class.

         :param name: The description of the review.
         :type name: str
         :param description: The rating of the review.
         :type description: float

         The constructor creates a review with the specified description and rating, and assigns a unique identifier to it.



Module Contents
---------------

Classes
~~~~~~~

.. autoapisummary::

   app.model.review.Review




.. py:class:: Review(description, rating)



