==================
/voter/:id/record/
==================

A representation of a voter's party affiliation and voting record for a set of
elections. Only the `detail`_ endpoint is supported for this resource.

Detail
======

Resource URL
------------

https://api.votizen.com/v1/voter/:id/record/

Parameters
----------

No parameters are supported for the detail endpoint.

Example Request
---------------

GET https://api.votizen.com/v1/voter/161935062/record/?format=json&api_key=:api_key

::

    {
        "id": "161935062",
        "resource_uri": "/v1/voter/303381664/record/",
        "party": "Independent",
        "voting_history": [
            {
                "date": "2004-11-02",
                "voted": "Yes"
            },
            {
                "date": "2006-03-07",
                "voted": "No"
            },
            {
                "date": "2006-11-07",
                "voted": "No"
            },
            {
                "date": "2008-03-04",
                "voted": "No"
            },
            {
                "date": "2008-11-04",
                "voted": "Yes"
            },
            {
                "date": "2010-03-02",
                "voted": "No"
            },
            {
                "date": "2010-11-02",
                "voted": "No"
            }
        ]
    }

Fields
------

A schema containing field descriptions can be obtained from:

TODO: provide link to schema

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

