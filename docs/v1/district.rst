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

Resource URL
------------

https://api.votizen.com/v1/district/

Parameters
----------

Required parameters are in **bold**.

==========================   =============================================
Name                         Description
==========================   =============================================
**lon**                      Location longitude in degrees (SRID 4326)
**lat**                      Location latitude in degrees (SRID 4326)
precision                    Precision of location information (optional,
                             default value is "intersection")
==========================   =============================================

Enumerations
------------

**Precision**

==========================   =============================================
Value                        Description
==========================   =============================================
intersection                 Exact location
range                        Location precise to within a street house
                             number range
street                       Location precise to within a street
zip                          Location precise to within a zip code
city                         Location precise to within a city
==========================   =============================================

Example Request
---------------

GET https://api.votizen.com/v1/district/?format=json&api_key=:api_key&lon=-122.40748&lat=37.78795&precision=city

::

    {
        "meta": {
            "previous": null,
            "total_count": 4,
            "offset": 0,
            "limit": 20,
            "next": null
        },
        "objects": [
            {
                "display_name": "the United States",
                "name": "United States of America",
                "short_name": "US",
                "type": "Nation",
                "demonym": "American",
                "races": [
                    "/v1/race/1/"
                ],
                "nickname": "",
                "id": "37",
                "website_url": "http://www.usa.gov/",
                "resource_uri": "/v1/district/37/"
            },
            {
                "display_name": "the State of California",
                "name": "California",
                "short_name": "CA",
                "type": "State",
                "demonym": "Californian",
                "races": [
                    "/v1/race/58/"
                ],
                "nickname": "The Golden State",
                "id": "42",
                "website_url": "http://www.ca.gov/",
                "resource_uri": "/v1/district/42/"
            },
            {
                "display_name": "the City of San Francisco, California",
                "name": "San Francisco",
                "short_name": "San Francisco, CA",
                "type": "City",
                "demonym": "San Franciscan",
                "races": [
                    "/v1/race/1549/",
                    "/v1/race/1550/"
                ],
                "nickname": "",
                "id": "37946",
                "website_url": "http://www.sfgov.org/",
                "resource_uri": "/v1/district/37946/"
            },
            {
                "display_name": "San Francisco County, California",
                "name": "San Francisco",
                "short_name": "San Francisco County, CA",
                "type": "County",
                "demonym": "",
                "races": [],
                "nickname": "",
                "id": "65276",
                "website_url": "http://www.sfgov.org/",
                "resource_uri": "/v1/district/65276/"
            }
        ]
    }

