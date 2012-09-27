===============
Getting Started
===============

The Votizen API is a collection of interfaces which provides access to the
nouns of the political process, such as :doc:`candidates </v1/candidate>`,
:doc:`political districts </v1/district>`, and :doc:`voters </v1/voter>`.

.. note::

    Voter data may only be used for political purposes. Commercial use is
    prohibited by law.


Obtaining an API Key
====================

An API key is a unique identifier and a secret token for authentication
provided by Votizen and is required for developers to access the API.

To obtain an API key:

    1. `Sign up`_ on Votizen.
    2. Send an e-mail to developer@votizen.com with the following information:

        - Developer Name
        - Organization Name
        - A short description and purpose of the application(s) which will be
          accessing the API.

An engineer from Votizen will respond within one business day with additional
instructions along with a newly minted API key.

.. _Sign up: https://www.votizen.com/signup

Don't forget to join the `Votizen API Developer Group`_ to ask questions and
share feedback about the Votizen API. Feedback and involvement from each and
every developer is paramount for building an elegant, timeless API that
everybody in developer community can benefit from.

.. _Votizen API Developer Group: http://groups.google.com/group/votizen-api



Using the Votizen API
=====================

The Votizen API is entirely HTTP-based and accessible via the base URL::

    https://api.votizen.com/v1/

Developers must authenticate all requests by providing the API key to each
request via the ``api_key`` parameter::

    https://api.votizen.com/v1/voter/?format=json&api_key=:api_key&first_name=Alaska&last_name=Voter


SSL Access
==========

The Votizen API is only available over HTTPS.


Supported Response Formats
==========================

The Votizen API presently supports the `JSON`_ format. Please send an e-mail to
developer@votizen.com if you would like to see other response formats
supported.

.. _JSON: http://www.json.org


Troubleshooting
===============

Having trouble? We'd like to help!

    - Double-check the HTTP response headers and body. The status code of the
      response should indicate the nature of the error.

    - Search the `Votizen API Developer Group`_ for answers. If there aren't
      any helpful posts, create a new post with at least the following
      information:

        - The request that is failing and the response and its headers that are
          sent back.
        - If available, a link to a web page that demonstrates the problem.
