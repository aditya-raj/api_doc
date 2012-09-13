============
Introduction
============

Constructing URLs
=================

Base URL
--------
All URLs referenced in this documentation have the following base:

    https://api.votizen.com/v1/
    
We currently support only the HTTPS protocol.

Resource Naming
---------------
The Votizen APIs are based on REST principles.  Resource lookups are generalized 
to a URI format that attempts to conform to the following conventions:

* Path variables encode hierarchy (such as: voters/california/sacramento/)
* Punctuation is used to avoid implying hierarchy where none exists (such as: 
  voters/geocode/lat,lon)
* Query strings are used to conduct searches (such as:
  voters/?last_name=washington&dob_year=1976&state=virginia)

Authentication
--------------
Access to the APIs is controlled with the use of API keys.  Your
Votizen-assigned API key will be provided in each of your requests via the
api_key parameter.

Rate Limiting
-------------

Calls to the APIs are rate limited to 350 per hour. HTTP headers are included
in responses to indicate the current rate limit, how many calls remain, and
when the calls remaining will be reset back to the limit::

    X-Ratelimit-Limit: 350
    X-Ratelimit-Remaining: 257
    X-Ratelimit-Reset: 1345696749

Request/Response Format
=======================
Requests are made via standard HTTP methods: GET, POST, PUT, and DELETE.  All
responses are returned as standard JSON objects.

Retrieving Resources with the HTTP GET Method
---------------------------------------------
Resource representations can be retrieved by GETing its URL.  This will return a
response code as follows:

======================= ============================================
Code                    Description
======================= ============================================
200 OK                  Request was successful.
302 FOUND               Redirect response.
304 NOT MODIFIED        Cached representation is up to date.
400 BAD REQUEST         General request error.
401 UNAUTHORIZED        Credentials were insufficient.
403 FORBIDDEN           Rate limit exceeded.
404 NOT FOUND           Resource not available at this URI.
405 METHOD NOT ALLOWED  HTTP Method not allowed for this resource.
500 SERVER ERROR        Internal Server Error.
503 SERVICE UNAVAILABLE Temporary server issue.
======================= ============================================


Creating/Updating Resources with the HTTP POST and PUT Methods
--------------------------------------------------------------
When available, resource representations may be created or updated via a POST or
PUT to a specified resource URL.  This will return a response code as follows:

======================= ============================================
Code                    Description
======================= ============================================
200 OK                  Request was successful and resource updated.
201 CREATED             Request was successful and resource created.
400 BAD REQUEST         The data submitted failed validation.
401 UNAUTHORIZED        Credentials were insufficient.
403 FORBIDDEN           Rate limit exceeded.
404 NOT FOUND           Resource not available at this URI.
405 METHOD NOT ALLOWED  HTTP Method not allowed for this resource.
500 SERVER ERROR        Internal Server Error.
======================= ============================================

Deleting Resources with the HTTP DELETE Methods
-----------------------------------------------
When available, resource representations may be deleted via a DELETE to a
specified resource URL.  This will return a response code as follows:

======================= ============================================
Code                    Description
======================= ============================================
204 OK                  Request was successful and resource deleted.
401 UNAUTHORIZED        Credentials were insufficient.
403 FORBIDDEN           Rate limit exceeded.
404 NOT FOUND           Resource not available at this URI.
405 METHOD NOT ALLOWED  HTTP Method not allowed for this resource.
500 SERVER ERROR        Internal Server Error.
======================= ============================================

Errors
------
Errors are returned as JSON objects with the following properties:

========    ======================================================
Property    Description
========    ======================================================
message     A more descriptive message regarding the exception.
========    ======================================================


Resource Types
==============
Two types of representations are returned: detail resources and list
resources.

Detail Resources
------------------

Resources can be returned as specific representations of individual objects.
These can represent a individual voter, district, or other data object in the
system.  Detail requests are assumed to be called by that object's ID.


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

Dates and Times
---------------

All times are returned as 'YYYY-MM-DD HH:MM:SS' in UTC.
All dates are returned as 'YYYY-MM-DD' in UTC.


Resource Descriptions
=====================

The :doc:`apis` page has information on the available APIs and resources.
