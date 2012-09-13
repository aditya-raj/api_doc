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

Resource URL
------------

https://api.votizen.com/v1/candidate/

Parameters
----------

All parameters are optional.

==========================   =============================================
Name                         Description
==========================   =============================================
id                           Candidate id
race_id                      Race id in which a candidate is running
                             (multiple values will yield a UNION result)
==========================   =============================================

Example Request
---------------

GET https://api.votizen.com/v1/candidate/?format=json&api_key=:api_key&race_id=1&race_id=58

::

    {
        "meta": {
            "previous": null,
            "total_count": 8,
            "offset": 0,
            "limit": 20,
            "next": null
        },
        "objects": [
            {
                "website": "http://www.barackobama.com/",
                "first_name": "Barack",
                "last_name": "Obama",
                "middle_name": "H.",
                "race": [
                    "/v1/race/1/"
                ],
                "party": "Democratic",
                "nickname": "Barack",
                "id": "1",
                "resource_uri": "/v1/candidate/1/"
            },
            {
                "website": "http://www.mittromney.com/",
                "first_name": "Willard",
                "last_name": "Romney",
                "middle_name": "Mitt",
                "race": [
                    "/v1/race/1/"
                ],
                "party": "Republican",
                "nickname": "Mitt",
                "id": "2",
                "resource_uri": "/v1/candidate/2/"
            },
            {
                "website": "http://www.garyjohnson2012.com/",
                "first_name": "Gary",
                "last_name": "Johnson",
                "middle_name": "",
                "race": [
                    "/v1/race/1/"
                ],
                "party": "Libertarian",
                "nickname": "",
                "id": "11",
                "resource_uri": "/v1/candidate/11/"
            },
            {
                "website": "http://www.diannefeinstein2012.com/",
                "first_name": "Dianne",
                "last_name": "Feinstein",
                "middle_name": "",
                "race": [
                    "/v1/race/58/"
                ],
                "party": "Democratic",
                "nickname": "",
                "id": "18",
                "resource_uri": "/v1/candidate/18/"
            },
            {
                "website": "http://www.emken2012.com/",
                "first_name": "Elizabeth",
                "last_name": "Emken",
                "middle_name": "",
                "race": [
                    "/v1/race/58/"
                ],
                "party": "Republican",
                "nickname": "",
                "id": "30",
                "resource_uri": "/v1/candidate/30/"
            },
            {
                "website": "http://www.voterocky.org/",
                "first_name": "Ross",
                "last_name": "Anderson",
                "middle_name": "",
                "race": [
                    "/v1/race/1/"
                ],
                "party": "Other",
                "nickname": "Rocky",
                "id": "320",
                "resource_uri": "/v1/candidate/320/"
            },
            {
                "website": "http://www.jillstein.org/",
                "first_name": "Jill",
                "last_name": "Stein",
                "middle_name": "Marie",
                "race": [
                    "/v1/race/1/"
                ],
                "party": "Green",
                "nickname": "",
                "id": "322",
                "resource_uri": "/v1/candidate/322/"
            },
            {
                "website": "http://socialequality.com/",
                "first_name": "Jerome",
                "last_name": "White",
                "middle_name": "",
                "race": [
                    "/v1/race/1/"
                ],
                "party": "Other",
                "nickname": "Jerry",
                "id": "324",
                "resource_uri": "/v1/candidate/324/"
            }
        ]
    }

