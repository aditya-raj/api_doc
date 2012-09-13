==========
/race/
==========

A representation of a political race. A race is defined as a set of candidates
running for an office on a certain date within a specific district. Both
`detail`_ and `list`_ endpoints are supported for this resource.

Detail
======

Resource URL
------------

https://api.votizen.com/v1/race/:id/

Parameters
----------

No parameters are supported for the detail endpoint.

Example Request
---------------

GET https://api.votizen.com/v1/race/1/?format=json&api_key=:api_key

::

    {
        "id": "1",
        "resource_uri": "/v1/race/1/",
        "district": {
            "id": "37",
            "resource_uri": "/v1/district/37/",
            "display_name": "the United States",
            "name": "United States of America",
            "short_name": "US",
            "type": "Nation",
            "nickname": "",
            "demonym": "American",
            "website_url": "http://www.usa.gov/",
            "races": [
                "/v1/race/1/"
            ]
        },
        "office": {
            "id": "1",
            "resource_uri": "/v1/office/1/",
            "term_length": 4,
            "level": "Federal",
            "title": "President",
            "short_title": "President",
            "chamber": null,
            "executive_rank": "Primary",
            "branch": "Executive",
            "website_url": "http://www.whitehouse.gov/",
            "races": [
                "/v1/race/1/"
            ]
        },
        "election_date": "2012-11-06",
        "candidates": [
            {
                "id": "11",
                "resource_uri": "/v1/candidate/11/",
                "first_name": "Gary",
                "last_name": "Johnson",
                "middle_name": "",
                "party": "Libertarian",
                "nickname": "",
                "website": "http://www.garyjohnson2012.com/",
                "race": [
                    "/v1/race/1/"
                ]
            },
            {
                "id": "322",
                "resource_uri": "/v1/candidate/322/",
                "first_name": "Jill",
                "last_name": "Stein",
                "middle_name": "Marie",
                "party": "Green",
                "nickname": "",
                "website": "http://www.jillstein.org/",
                "race": [
                    "/v1/race/1/"
                ]
            },
            {
                "id": "324",
                "resource_uri": "/v1/candidate/324/",
                "first_name": "Jerome",
                "last_name": "White",
                "middle_name": "",
                "party": "Other",
                "nickname": "Jerry",
                "website": "http://socialequality.com/",
                "race": [
                    "/v1/race/1/"
                ]
            },
            {
                "id": "320",
                "resource_uri": "/v1/candidate/320/",
                "first_name": "Ross",
                "last_name": "Anderson",
                "middle_name": "",
                "party": "Other",
                "nickname": "Rocky",
                "website": "http://www.voterocky.org/",
                "race": [
                    "/v1/race/1/"
                ]
            },
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
            },
            {
                "id": "2",
                "resource_uri": "/v1/candidate/2/",
                "first_name": "Willard",
                "last_name": "Romney",
                "middle_name": "Mitt",
                "party": "Republican",
                "nickname": "Mitt",
                "website": "http://www.mittromney.com/",
                "race": [
                    "/v1/race/1/"
                ]
            }
        ]
    }


Fields
------

A schema containing field descriptions can be obtained from:

https://api.votizen.com/v1/race/schema/?format=json&api_key=:api_key

List
====

Resource URL
------------

https://api.votizen.com/v1/race/

Parameters
----------

All parameters are optional.

==========================   =============================================
Name                         Description
==========================   =============================================
id                           Race id
==========================   =============================================

**Search by location**

==========================   =============================================
Name                         Description
==========================   =============================================
street                       Street address
city                         City
state                        State
zip                          Zip code
==========================   =============================================

Example Request
---------------

GET https://api.votizen.com/v1/race/?format=json&api_key=:api_key&street=1+The+Embarcadero&city=San+Francisco&state=CA&zip=94105

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
                "district": {
                    "races": [
                        "/v1/race/1/"
                    ],
                    "display_name": "the United States",
                    "name": "United States of America",
                    "short_name": "US",
                    "type": "Nation",
                    "nickname": "",
                    "demonym": "American",
                    "id": "37",
                    "website_url": "http://www.usa.gov/",
                    "resource_uri": "/v1/district/37/"
                },
                "office": {
                    "races": [
                        "/v1/race/1/"
                    ],
                    "id": "1",
                    "term_length": 4,
                    "level": "Federal",
                    "title": "President",
                    "short_title": "President",
                    "chamber": null,
                    "executive_rank": "Primary",
                    "branch": "Executive",
                    "website_url": "http://www.whitehouse.gov/",
                    "resource_uri": "/v1/office/1/"
                },
                "election_date": "2012-11-06",
                "candidates": [
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
                    }
                ],
                "id": "1",
                "resource_uri": "/v1/race/1/"
            },
            {
                "district": {
                    "races": [
                        "/v1/race/58/"
                    ],
                    "display_name": "the State of California",
                    "name": "California",
                    "short_name": "CA",
                    "type": "State",
                    "nickname": "The Golden State",
                    "demonym": "Californian",
                    "id": "42",
                    "website_url": "http://www.ca.gov/",
                    "resource_uri": "/v1/district/42/"
                },
                "office": {
                    "races": [
                        "/v1/race/62/",
                        "/v1/race/58/",
                        "/v1/race/85/",
                        "/v1/race/87/",
                        "/v1/race/68/",
                        "/v1/race/89/",
                        "/v1/race/91/",
                        "/v1/race/95/",
                        "/v1/race/76/",
                        "/v1/race/72/",
                        "/v1/race/97/",
                        "/v1/race/80/",
                        "/v1/race/98/",
                        "/v1/race/100/",
                        "/v1/race/102/",
                        "/v1/race/103/",
                        "/v1/race/105/",
                        "/v1/race/74/",
                        "/v1/race/107/",
                        "/v1/race/66/",
                        "/v1/race/111/",
                        "/v1/race/112/",
                        "/v1/race/114/",
                        "/v1/race/115/",
                        "/v1/race/117/",
                        "/v1/race/64/",
                        "/v1/race/78/",
                        "/v1/race/119/",
                        "/v1/race/70/",
                        "/v1/race/121/",
                        "/v1/race/123/",
                        "/v1/race/125/",
                        "/v1/race/520/"
                    ],
                    "id": "2",
                    "term_length": 6,
                    "level": "Federal",
                    "title": "Senator",
                    "short_title": "Sen.",
                    "chamber": "Upper",
                    "executive_rank": null,
                    "branch": "Legislative",
                    "website_url": "http://www.senate.gov/",
                    "resource_uri": "/v1/office/2/"
                },
                "election_date": "2012-11-06",
                "candidates": [
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
                    }
                ],
                "id": "58",
                "resource_uri": "/v1/race/58/"
            },
            {
                "district": {
                    "races": [
                        "/v1/race/1549/",
                        "/v1/race/1550/"
                    ],
                    "display_name": "the City of San Francisco, California",
                    "name": "San Francisco",
                    "short_name": "San Francisco, CA",
                    "type": "City",
                    "nickname": "",
                    "demonym": "San Franciscan",
                    "id": "37946",
                    "website_url": "http://www.sfgov.org/",
                    "resource_uri": "/v1/district/37946/"
                },
                "office": {
                    "races": [
                        "/v1/race/1549/"
                    ],
                    "id": "21999",
                    "term_length": 4,
                    "level": "Local",
                    "title": "School Board Member",
                    "short_title": "Mem.",
                    "chamber": null,
                    "executive_rank": "Teriary",
                    "branch": "Executive",
                    "website_url": "",
                    "resource_uri": "/v1/office/21999/"
                },
                "election_date": "2012-11-06",
                "candidates": [
                    {
                        "website": "",
                        "first_name": "Matt",
                        "last_name": "Haney",
                        "middle_name": "",
                        "race": [
                            "/v1/race/1549/"
                        ],
                        "party": "Democratic",
                        "nickname": "",
                        "id": "6645",
                        "resource_uri": "/v1/candidate/6645/"
                    },
                    {
                        "website": "http://beverlypopek2012.nationbuilder.com/",
                        "first_name": "Beverly",
                        "last_name": "Popek",
                        "middle_name": "",
                        "race": [
                            "/v1/race/1549/"
                        ],
                        "party": "Democratic",
                        "nickname": "",
                        "id": "3851",
                        "resource_uri": "/v1/candidate/3851/"
                    },
                    {
                        "website": "http://www.sandrafewer.com/",
                        "first_name": "Sandra",
                        "last_name": "Fewer",
                        "middle_name": "Lee",
                        "race": [
                            "/v1/race/1549/"
                        ],
                        "party": "Democratic",
                        "nickname": "",
                        "id": "6670",
                        "resource_uri": "/v1/candidate/6670/"
                    },
                    {
                        "website": "http://www.jillwynns.com/",
                        "first_name": "Jill",
                        "last_name": "Wynns",
                        "middle_name": "",
                        "race": [
                            "/v1/race/1549/"
                        ],
                        "party": "Democratic",
                        "nickname": "",
                        "id": "6671",
                        "resource_uri": "/v1/candidate/6671/"
                    },
                    {
                        "website": "http://www.rachelnorton.com/",
                        "first_name": "Rachel",
                        "last_name": "Norton",
                        "middle_name": "",
                        "race": [
                            "/v1/race/1549/"
                        ],
                        "party": "Democratic",
                        "nickname": "",
                        "id": "6672",
                        "resource_uri": "/v1/candidate/6672/"
                    },
                    {
                        "website": "http://deanclarkforschoolboard.blogspot.com/",
                        "first_name": "Dean",
                        "last_name": "Clark",
                        "middle_name": "",
                        "race": [
                            "/v1/race/1549/"
                        ],
                        "party": "Democratic",
                        "nickname": "",
                        "id": "6673",
                        "resource_uri": "/v1/candidate/6673/"
                    }
                ],
                "id": "1549",
                "resource_uri": "/v1/race/1549/"
            },
            {
                "district": {
                    "races": [
                        "/v1/race/1549/",
                        "/v1/race/1550/"
                    ],
                    "display_name": "the City of San Francisco, California",
                    "name": "San Francisco",
                    "short_name": "San Francisco, CA",
                    "type": "City",
                    "nickname": "",
                    "demonym": "San Franciscan",
                    "id": "37946",
                    "website_url": "http://www.sfgov.org/",
                    "resource_uri": "/v1/district/37946/"
                },
                "office": {
                    "races": [
                        "/v1/race/1550/"
                    ],
                    "id": "22000",
                    "term_length": 4,
                    "level": "Local",
                    "title": "College Board Member",
                    "short_title": "Mem.",
                    "chamber": null,
                    "executive_rank": "Teriary",
                    "branch": "Executive",
                    "website_url": "",
                    "resource_uri": "/v1/office/22000/"
                },
                "election_date": "2012-11-06",
                "candidates": [
                    {
                        "website": "http://www.santos2012.com/",
                        "first_name": "Rodrigo",
                        "last_name": "Santos",
                        "middle_name": "",
                        "race": [
                            "/v1/race/1550/"
                        ],
                        "party": "Democratic",
                        "nickname": "",
                        "id": "3852",
                        "resource_uri": "/v1/candidate/3852/"
                    },
                    {
                        "website": "",
                        "first_name": "Natalie",
                        "last_name": "Berg",
                        "middle_name": "",
                        "race": [
                            "/v1/race/1550/"
                        ],
                        "party": "Democratic",
                        "nickname": "",
                        "id": "6674",
                        "resource_uri": "/v1/candidate/6674/"
                    },
                    {
                        "website": "",
                        "first_name": "Milton",
                        "last_name": "Marks",
                        "middle_name": "",
                        "race": [
                            "/v1/race/1550/"
                        ],
                        "party": "Unknown",
                        "nickname": "",
                        "id": "6676",
                        "resource_uri": "/v1/candidate/6676/"
                    },
                    {
                        "website": "http://votechrisjackson.nationbuilder.com/",
                        "first_name": "Chris",
                        "last_name": "Jackson",
                        "middle_name": "",
                        "race": [
                            "/v1/race/1550/"
                        ],
                        "party": "Democratic",
                        "nickname": "",
                        "id": "6675",
                        "resource_uri": "/v1/candidate/6675/"
                    },
                    {
                        "website": "http://stevengo.nationbuilder.com/",
                        "first_name": "Steve",
                        "last_name": "Ngo",
                        "middle_name": "",
                        "race": [
                            "/v1/race/1550/"
                        ],
                        "party": "Democratic",
                        "nickname": "",
                        "id": "6677",
                        "resource_uri": "/v1/candidate/6677/"
                    },
                    {
                        "website": "http://www.amybacharach.com/",
                        "first_name": "Amy",
                        "last_name": "Bacharach",
                        "middle_name": "",
                        "race": [
                            "/v1/race/1550/"
                        ],
                        "party": "Democratic",
                        "nickname": "",
                        "id": "6678",
                        "resource_uri": "/v1/candidate/6678/"
                    }
                ],
                "id": "1550",
                "resource_uri": "/v1/race/1550/"
            }
        ]
    }

