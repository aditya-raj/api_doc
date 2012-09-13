==========
/voter/
==========

A representation of a voter. Both `detail`_ and `list`_ endpoints are
supported for this resource.

Detail
======

Resource URL
------------

https://api.votizen.com/v1/voter/:id/

Parameters
----------

No parameters are supported for the detail endpoint.

Example Request
---------------

GET https://api.votizen.com/v1/voter/161935062/?format=json&api_key=:api_key

::

    {
        "id": "161935062",
        "resource_uri": "/v1/voter/161935062/",
        "is_registered_voter": true,
        "voter_data_uris": {
            "voter_record_uri": "/v1/voter/161935062/record/"
        }
    }

Fields
------

A schema containing field descriptions can be obtained from:

https://api.votizen.com/v1/voter/schema/?format=json&api_key=:api_key

List
====

Resource URL
------------

https://api.votizen.com/v1/voter/

Parameters
----------

All parameters are optional.

==========================   =============================================
Name                         Description
==========================   =============================================
id                           Voter id
first_name                   First Name
middle_name                  Middle Name
last_name                    Last Name
street                       Street address
city                         City
state                        State
zip                          Zip code
dob_year                     Birth year
dob_month                    Birth month
dob_day                      Birth day of month
==========================   =============================================

Example Request
---------------

GET https://api.votizen.com/v1/voter/?format=json&api_key=:api_key&first_name=Alaska&last_name=Voter&city=Juneau&state=AK

::

    {
        "meta": {
            "previous": null,
            "total_count": 1,
            "offset": 0,
            "limit": 20,
            "next": null
        },
        "objects": [
            {
                "id": "161935062",
                "resource_uri": "/v1/voter/161935062/",
                "is_registered_voter": true,
                "voter_data_uris": {
                    "voter_record_uri": "/v1/voter/161935062/record/"
                }
            }
        ]
    }

