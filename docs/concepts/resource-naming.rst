===============
Resource Naming
===============

The Votizen API attempts to conform to the design principles of
`Representational State Transfer (REST)`_. Resource lookups are generalized to
a URI format that conforms to the following conventions:

    - Path variables encode hierarchy (e.g. voters/california/sacramento/)
    - Punctuation is used to avoid implying hierarchy where none exists (e.g.
      voters/geocode/lat,lon)
    - Query strings are used to conduct searches (e.g.
      voters/?last_name=washington&dob_year=1976&state=virginia)

.. _Representational State Transfer (REST): http://en.wikipedia.org/wiki/Representational_state_transfer


Resource Types
==============

Two types of resource representations are available: detail resources and list
resources.


Detail Resources
----------------

Resources can be returned as specific representations of individual objects.
These can represent an individual voter, district, or other data object in the
database. Detail requests are assumed to be called by that object's ID.


List Resources
--------------

Some resources are lists of other resources, and these results are paginated by
the API.  Resource list responses include the following pagination information
in the response's ``meta`` property:

=========== ===============================================================
Property    Description
=========== ===============================================================
previous    The previous page number.
total_count The total number of items on the list.
offset      The position in the overall list of the first item in the page.
limit       The number of items in this page.
next        The next page number.
=========== ===============================================================
