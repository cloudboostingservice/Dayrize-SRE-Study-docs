:py:mod:`app.controllers.auth`
==============================

.. py:module:: app.controllers.auth

.. autoapi-nested-parse::

   Authentication Controller
   =========================

   This module handles authentication flows for the application by interfacing with Auth0. It provides endpoints for initiating the login process and handling callbacks from Auth0 upon successful authentication. The module utilizes environment variables for configuration and leverages Flask and Flask-Loguru for routing and logging, respectively.

   Blueprints:
       auth: A Flask Blueprint that defines routes for authentication processes including login initiation and callback handling.

   Functions:
       login() -> str:
           Initiates the login process by constructing and returning the URL for the Auth0 login page. This function constructs the URL with necessary parameters including the response type, client ID, and redirect URI, then logs and returns this URL for redirecting the user to Auth0's hosted login page. Potential issues may arise from missing or incorrect environment variable configurations.

       callback() -> dict or str:
           Handles the authentication callback from Auth0. This function is responsible for processing the authentication response received at the callback URL. It extracts the ID token from the response and returns it. Errors may occur if the callback does not include an ID token or if there are issues parsing the response.

   Environment Variables:
       AUTH0_DOMAIN (str): The Auth0 domain, used for constructing authentication URLs.
       AUTH0_CLIENT_ID (str): The client ID for the Auth0 application, used in authentication requests.
       DEPLOYMENT_DOMAIN (str): The domain where the application is deployed, used for redirect URIs in authentication flows.

   Exceptions:
       - `MissingEnvironmentVariableError`: Raised if any required environment variables (AUTH0_DOMAIN, AUTH0_CLIENT_ID, DEPLOYMENT_DOMAIN) are not set or are incorrect, leading to failed construction of authentication URLs.
       - `AuthCallbackError`: Custom exception raised if the callback handler encounters issues, such as missing ID token in the response.



Module Contents
---------------


Functions
~~~~~~~~~

.. autoapisummary::

   app.controllers.auth.login
   app.controllers.auth.callback



Attributes
~~~~~~~~~~

.. autoapisummary::

   app.controllers.auth.auth_controller


.. py:data:: auth_controller

   

.. py:function:: login()

   Initiates the login process.

   Constructs and returns the Auth0 login URL, redirecting the user to the Auth0 hosted login page.

   :return: The URL for the Auth0 login page.


.. py:function:: callback()

   Handles the authentication callback.

   Extracts and returns the ID token from the Auth0 authentication response.

   :return: The ID token from the Auth0 callback.


