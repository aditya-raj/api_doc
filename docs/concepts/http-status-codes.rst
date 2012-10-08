==================================
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

