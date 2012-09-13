==========
/district/
==========

A representation of a political district. Only the `detail`_ endpoint is
supported for this resource.

Detail
======

Resource URL
------------

https://api.votizen.com/v1/district/:id/

Parameters
----------

No parameters are supported for the detail endpoint.

Example Request
---------------

GET https://api.votizen.com/v1/district/37/?format=json&api_key=:api_key

::

    {
        "id": "37",
        "resource_uri": "/v1/district/37/",
        "name": "United States of America",
        "display_name": "the United States",
        "short_name": "US",
        "type": "Nation",
        "nickname": "",
        "demonym": "American",
        "website_url": "http://www.usa.gov/",
        "races": [
            "/v1/race/1/"
        ]
    }

Fields
------

A schema containing field descriptions can be obtained from:

https://api.votizen.com/v1/district/schema/?format=json&api_key=:api_key

Enumerations
------------

**Type**

==========================   ============================================
Value                        Description
==========================   ============================================
Nation                       Nation district (currently only US)
State                        State district (also used for Senate)
County                       County district
City                         City district
School                       School district
Legislative (Nation Lower)   Congressional district
Legislative (State Upper)    State senate district
Legislative (State Lower)    State congressional district
==========================   ============================================

List
====

A list endpoint for this resource is not yet supported.

