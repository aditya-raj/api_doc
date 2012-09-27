:tocdepth: 1

====================
Limits & Suspensions
====================

Developers accessing the Votizen API may at no cost generate up to 350 requests
per hour. Additional HTTP headers are included in each response which indicates
the current limit ceiling, the number of calls remaining, and the timestamp of
when the calls remaining will be reset back to the limit ceiling::

    X-Ratelimit-Limit: 350
    X-Ratelimit-Remaining: 257
    X-Ratelimit-Reset: 1345696749

The Votizen API will return a HTTP 403 status code to indicate that the limit
has been exceeded. Developers who exceed these usage limits must respond in one
of the following ways to continue using the Votizen API:

    - Modify the application such that the number of requests made in an hour
      is below the usage limit.
    - Contact the Votizen API Business Sales team at developer@votizen.com for
      more information how to purchase additional quota.

Multiple violations of attempting to access the Votizen API while over the rate
limit will result in a suspension of the API key. A courtesy notice will be
sent to the developer before the API key is suspended. The Votizen API will
always respond with HTTP 401 status codes when requests are made with a
suspended API key.


Suspensions
===========

Developers who violate the Votizen API Terms of Service will have their API key
suspended. Please review the terms to find out more about specific violations.


Repealing a Suspension
======================

Please send an e-mail to developer@votizen.com with the following information
in the body of the e-mail:

    - The full name of the developer who registered for the API key.
    - A brief description of how the application interacts with the Votizen
      API.

Attempts to register a new API key while a suspension is in place is a
violation of our API Terms of Service and may result in a permanent suspension
on all associated developer accounts.
