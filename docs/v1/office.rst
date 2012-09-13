==========
/office/
==========

A representation of a political office. Only the `detail`_ endpoint is
supported for this resource.

Detail
======

Resource URL
------------

https://api.votizen.com/v1/office/:id/

Parameters
----------

No parameters are supported for the detail endpoint.

Example Request
---------------

GET https://api.votizen.com/v1/office/1/?format=json&api_key=:api_key

::

    {
        "id": "1",
        "resource_uri": "/v1/office/1/",
        "title": "President",
        "short_title": "President",
        "level": "Federal",
        "branch": "Executive",
        "chamber": null,
        "executive_rank": "Primary",
        "term_length": 4,
        "website_url": "http://www.whitehouse.gov/",
        "races": [
            "/v1/race/1/"
        ]
    }

Fields
------

A schema containing field descriptions can be obtained from:

https://api.votizen.com/v1/office/schema/?format=json&api_key=:api_key

Enumerations
------------

**Level**

==========================   =============================================
Value                        Description
==========================   =============================================
Federal                      Federal level office
State                        State level office
County                       County level office
Local                        City level office
==========================   =============================================

**Branch**

==========================   =============================================
Value                        Description
==========================   =============================================
Executive                    Executive branch
Legislative                  Legislative branch
==========================   =============================================

**Chamber**

==========================   =============================================
Value                        Description
==========================   =============================================
Lower                        Lower chamber (e.g. House of Representatives)
Upper                        Upper chamber (e.g. Senate)
==========================   =============================================

**Executive Rank**

==========================   =============================================
Value                        Description
==========================   =============================================
Primary                      Primary rank (e.g. President)
Secondary                    Secondary rank (e.g. Vice President)
Tertiary                     Tertiary rank (e.g. Cabinet member)
==========================   =============================================

List
====

A list endpoint for this resource is not yet supported.

