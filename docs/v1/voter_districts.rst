=====================
/voter/:id/districts/
=====================

A list of the voter's districts. Only the `detail`_ endpoint is supported for 
this resource.

The :doc:`/v1/voter` resource can be used for identifying specific voters.

Detail
======

This endpoint is equivalent to querying the :doc:`/v1/district` endpoint with 
the latitude and longitude of the voter's registered address.

Resource URL
------------

https://api.votizen.com/v1/voter/:id/districts/

Parameters
----------

No parameters are supported for the detail endpoint.

Example Request
---------------

GET https://api.votizen.com/v1/voter/161935062/districts/?format=json&api_key=:api_key

::

    {
        "meta": {
            "limit": 20,
            "next": null,
            "offset": 0,
            "previous": null,
            "total_count": 8
        },
        "objects": [
            {
                "demonym": "American",
                "display_name": "the United States",
                "id": "37",
                "name": "United States of America",
                "nickname": "",
                "races": [
                    "/v1/race/1/"
                ],
                "resource_uri": "/v1/district/37/",
                "short_name": "US",
                "type": "Nation",
                "website_url": "http://www.usa.gov/"
            },
            {
                "demonym": "Alaskan",
                "display_name": "the State of Alaska",
                "id": "39",
                "name": "Alaska",
                "nickname": "The Last Frontier",
                "races": [ ],
                "resource_uri": "/v1/district/39/",
                "short_name": "AK",
                "type": "State",
                "website_url": "http://www.alaska.gov"
            },
            {
                "demonym": "",
                "display_name": "Alaska",
                "id": "108",
                "name": "Congressional District (at Large)",
                "nickname": "",
                "races": [
                    "/v1/race/4594/"
                ],
                "resource_uri": "/v1/district/108/",
                "short_name": "0",
                "type": "Legislative (Nation Lower)",
                "website_url": ""
            },
            {
                "demonym": "",
                "display_name": "the 32nd District",
                "id": "1039",
                "name": "State House District 32, Chugach State Park",
                "nickname": "",
                "races": [ ],
                "resource_uri": "/v1/district/1039/",
                "short_name": "32",
                "type": "Legislative (State Lower)",
                "website_url": ""
            },
            {
                "demonym": "",
                "display_name": "District B",
                "id": "9207",
                "name": "State Senate District B",
                "nickname": "",
                "races": [ ],
                "resource_uri": "/v1/district/9207/",
                "short_name": "B",
                "type": "Legislative (State Upper)",
                "website_url": ""
            },
            {
                "demonym": "",
                "display_name": "the City of Juneau, Alaska",
                "id": "36900",
                "name": "Juneau",
                "nickname": "",
                "races": [ ],
                "resource_uri": "/v1/district/36900/",
                "short_name": "Juneau, AK",
                "type": "City",
                "website_url": "http://www.traveljuneau.com/"
            },
            {
                "demonym": "",
                "display_name": "Juneau Borough, Alaska",
                "id": "65130",
                "name": "Juneau",
                "nickname": "",
                "races": [ ],
                "resource_uri": "/v1/district/65130/",
                "short_name": "Juneau Borough, AK",
                "type": "County",
                "website_url": "http://www.juneau.org/"
            },
            {
                "demonym": "",
                "display_name": "the Juneau Borough School District",
                "id": "80160",
                "name": "Juneau Borough School District",
                "nickname": "",
                "races": [ ],
                "resource_uri": "/v1/district/80160/",
                "short_name": "",
                "type": "Legislative (Unified School)",
                "website_url": ""
            }
        ]
    }

Fields & Enumerations
---------------------

For schema information please refer the Detail section of the 
:doc:`/v1/district` documentation.

List
====

A list endpoint for this resource is not yet supported.

