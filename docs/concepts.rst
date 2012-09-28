:tocdepth: 1

========
Concepts
========

API Stability
=============

The Votizen API is constantly evolving and will regularly be updated with new
features, bug fixes and performance improvements. All changes made to the API
within the current version will be backwards-compatible, ensuring that
launched applications using the presently documented endpoints will continue to
work without modification.

Features that are experimental will clearly be labled in the :doc:`apis` and
are not covered by this guarantee.


Dates & Times
=============

Dates and times are expressed according to `ISO 8601`_ and are returned in the
extended format::

    YYYY-MM-DD HH:MM:SS

The Votizen API most often returns a combined date and time in UTC which
represents a single point in time.

.. _ISO 8601: http://en.wikipedia.org/wiki/ISO_8601


HTTP Status Codes & Error Messages
==================================

The Votizen API responds with the appropriate HTTP status codes for all
requests.

======================= ============================================ =======
Code                    Description                                  Method
======================= ============================================ =======
200 OK                  Request was successful.                      GET
302 FOUND               Redirect response.                           GET
304 NOT MODIFIED        Cached representation is up to date.         GET
400 BAD REQUEST         General request error.                       GET
401 UNAUTHORIZED        Credentials were insufficient.               GET
403 FORBIDDEN           Rate limit exceeded.                         GET
404 NOT FOUND           Resource not available at this URI.          GET
405 METHOD NOT ALLOWED  HTTP Method not allowed for this resource.   GET
500 SERVER ERROR        Internal Server Error.                       GET
503 SERVICE UNAVAILABLE Temporary server issue.                      GET
======================= ============================================ =======


Error Handling
--------------

Applications should use the HTTP status code to determine the best way to
address errors. Any additional information is included in the body of the
response as JSON objects with the following properties:

========    ======================================================
Property    Description
========    ======================================================
message     A more descriptive message regarding the exception.
========    ======================================================


Resource Naming
===============

The Votizen API attempts to conform to the design principles of
`Representational State Transfer (REST)`_. Resource lookups are generalized to
a URI format that conforms to the following conventions:

    - Path variables encode hierarchy (e.g. voters/california/sacramento/)
    - Punctuation is used to avoid implying hierarchy where none exists (e.g.
      voters/geocode/lat,lon)
    - Query strings are used to conduct searches (e.g.
      voters/?last_name=washington&dob_year=1976&state=virginia)

.. _Representational State Transfer (REST): http://en.wikipedia.org/wiki/Representational_state_transfer


Resource Types
==============

Two types of resource representations are available: detail resources and list
resources.


Detail Resources
----------------

Resources can be returned as specific representations of individual objects.
These can represent an individual voter, district, or other data object in the
database. Detail requests are assumed to be called by that object's ID.


List Resources
--------------

Some resources are lists of other resources, and these results are paginated by
the API.  Resource list responses include the following pagination information
in the response's ``meta`` property:

=========== ===============================================================
Property    Description
=========== ===============================================================
previous    The previous page number.
total_count The total number of items on the list.
offset      The position in the overall list of the first item in the page.
limit       The number of items in this page.
next        The next page number.
=========== ===============================================================
