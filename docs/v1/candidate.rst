==========
/candidate/
==========

A representation of a political candidate running in a race. Only the `detail`_
endpoint is supported for this resource.

Detail
======

Resource URL
------------

https://api.votizen.com/v1/candidate/:id/

Parameters
----------

No parameters are supported for the detail endpoint.

Example Request
---------------

GET https://api.votizen.com/v1/candidate/1/?format=json&api_key=:api_key

::

    {
        "id": "1",
        "resource_uri": "/v1/candidate/1/",
        "first_name": "Barack",
        "last_name": "Obama",
        "middle_name": "H.",
        "party": "Democratic",
        "nickname": "Barack",
        "website": "http://www.barackobama.com/",
        "race": [
            "/v1/race/1/"
        ]
    }

Fields
------

A schema containing field descriptions can be obtained from:

https://api.votizen.com/v1/candidate/schema/?format=json&api_key=:api_key

Enumerations
------------

**Party**

==========================   ============================================
Value                        Description
==========================   ============================================
Democratic                   Democratic Party
Republican                   Republican Party
Green                        Green Party
Libertarian                  Libertarian Party
Independent                  Independent
Other                        Other (Party known but not enumerated)
Unknown                      Party unknown
==========================   ============================================

List
====

A list endpoint for this resource is not yet supported.


