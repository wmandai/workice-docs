Social Logins
===============
.. meta::
   :description: Built into a smart work flow that includes e-signatures for your freelancer e-contracts.
   :keywords: projects, invoices, deals, leads, crm, estimates, tickets, subscriptions, tasks, contacts, contracts, creditnotes, freelanceroffice

In addition to typical, form based authentication, `Workice CRM <https://workice.com>`__ also provides a simple, convenient way to authenticate with OAuth providers. 

.. TIP:: Workice CRM currently supports authentication with **Facebook, Twitter, LinkedIn, Google, GitHub and GitLab**

.. ATTENTION:: Before using Social Logins, you will have to enable it in **Settings** > **System Settings**. Activate the **Social Login** checkbox.

.. NOTE:: New user accounts will be created if they do not exist.

Facebook Configuration
""""""""""""""""""""""""
 - Start by creating a `Facebook Application on the Developers Console <https://developers.facebook.com/apps>`__.
 - Copy your newly created application **App ID** and **App Secret**
 - Open your .env file located in your Root folder and set ``FACEBOOK_CLIENT_ID={YOUR-APP-ID}`` and ``FACEBOOK_CLIENT_SECRET={YOUR-APP-SECRET}``.
 - Still in your facebook developer console, under **Valid OAuth Redirect URIs** enter your redirect url as ``https://your-domain.com/callback/facebook``. Example; If you have installed workice in https://example.com then the callback url will be ``https://example.com/callback/facebook``.
 - Now your users can login using Facebook.
   
Twitter Configuration
""""""""""""""""""""""""
 - Start by creating a `Twitter Application on the Developers Console <https://developer.twitter.com/en/dashboard>`__.
 - Copy your newly created application Consumer API Keys **API key** and **API secret key**
 - Open your .env file located in your Root folder and set ``TWITTER_CLIENT_ID={YOUR-API-KEY}`` and ``TWITTER_CLIENT_SECRET={YOUR-API-SECRET}``.
 - Still in your twitter developer console, under **Callback URLs** enter your redirect url as ``https://your-domain.com/callback/twitter``. Example; If you have installed workice in https://example.com then the callback url will be ``https://example.com/callback/twitter``.
   

Google Configuration
""""""""""""""""""""""""
 - Start by creating `Google Application on the Developers Console <https://console.developers.google.com>`__.
 - Copy your newly created application **Client ID** and **Client Secret**
 - Open your .env file located in your Root folder and set ``GOOGLE_CLIENT_ID={YOUR-CLIENT-ID}`` and ``GOOGLE_CLIENT_SECRET={YOUR-SECRET-KEY}``.
 - Still in your google developer console, under **Authorized redirect URIs** enter your redirect url as ``https://your-domain.com/callback/google``. Example; If you have installed workice in https://example.com then the callback url will be ``https://example.com/callback/google``.
   

Github Configuration
""""""""""""""""""""""""
 - Start by creating `Github Application on the Developers Console <https://github.com/settings/developers>`__.
 - Copy your newly created application **Client ID** and **Client Secret**
 - Open your .env file located in your Root folder and set ``GITHUB_CLIENT_ID={YOUR-CLIENT-ID}`` and ``GITHUB_CLIENT_SECRET={YOUR-SECRET-KEY}``.
 - Still in your github developer console, under **Authorization callback URL** enter your redirect url as ``https://your-domain.com/callback/github``. Example; If you have installed workice in https://example.com then the callback url will be ``https://example.com/callback/github``.
   

LinkedIn Configuration
""""""""""""""""""""""""
 - Start by creating `LinkedIn Application on the Developers Console <https://www.linkedin.com/developers/apps>`__.
 - Copy your newly created application **Client ID** and **Client Secret**
 - Open your .env file located in your Root folder and set ``LINKEDIN_CLIENT_ID={YOUR-CLIENT-ID}`` and ``LINKEDIN_CLIENT_SECRET={YOUR-SECRET-KEY}``.
 - Still in your linkedin developer console, under **Redirect URLs** enter your redirect url as ``https://your-domain.com/callback/linkedin``. Example; If you have installed workice in https://example.com then the callback url will be ``https://example.com/callback/linkedin``.
   

Gitlab Configuration
""""""""""""""""""""""""
 - Start by creating `Gitlab Application in Applications Settings <https://gitlab.com/profile/applications>`__.
 - Enter your **Redirect URI**. Example; If you have installed workice in https://example.com then the callback url will be ``https://example.com/callback/gitlab``. (Use 1 line per URI)
 - Under **Scopes** check the **API** checkbox to enable it
 - Copy your newly created application **Application ID** and **Secret**
 - Open your .env file located in your Root folder and set ``GITLAB_CLIENT_ID={YOUR-APPLICATION-ID}`` and ``GITLAB_CLIENT_SECRET={YOUR-SECRET-KEY}``.

