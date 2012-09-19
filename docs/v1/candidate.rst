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
        "nickname": "Barack",
        "party": "Democratic",
        "website": "http://www.barackobama.com/",
        "street": "PO Box 802798",
        "city": "Chicago",
        "state": "IL",
        "zip": "60680",
        "email": "",
        "phone": "312.698.3670",
        "fax": "",
        "facebook_username": "barackobama",
        "twitter_username": "BarackObama",
        "youtube_username": "BarackObamadotcom",
        "bio": "Born in Honolulu, Hawaii, Obama is a graduate of Columbia University and Harvard Law School, where he was the president of the Harvard Law Review. He was a community organizer in Chicago before earning his law degree. He worked as a civil rights attorney in Chicago and taught constitutional law at the University of Chicago Law School from 1992 to 2004. He served three terms representing the 13th District in the Illinois Senate from 1997 to 2004.\nFollowing an unsuccessful bid against the Democratic incumbent for a seat in the United States House of Representatives in 2000, Obama ran for United States Senate in 2004. Several events brought him to national attention during the campaign, including his victory in the March 2004 Democratic primary and his keynote address at the Democratic National Convention in July 2004. He won election to the U.S. Senate in Illinois in November 2004. His presidential campaign began in February 2007, and after a close campaign in the 2008 Democratic Party presidential primaries against Hillary Rodham Clinton, he won his party's nomination. In the 2008 presidential election, he defeated Republican nominee John McCain, and was inaugurated as president on January 20, 2009. In October 2009, Obama was named the 2009 Nobel Peace Prize laureate.\nAs president, Obama signed economic stimulus legislation in the form of the American Recovery and Reinvestment Act in February 2009 and the Tax Relief, Unemployment Insurance Reauthorization, and Job Creation Act in December 2010. Other domestic policy initiatives include the Patient Protection and Affordable Care Act, the Dodd–Frank Wall Street Reform and Consumer Protection Act, the Don't Ask, Don't Tell Repeal Act and the Budget Control Act of 2011. In foreign policy, he gradually withdrew combat troops from Iraq, increased troop levels in Afghanistan, signed the New START arms control treaty with Russia, ordered enforcement of the United Nations-sanctioned no-fly zone over Libya, and issued a direct order to a small group of American military forces to kill al-Qaeda leader Osama bin Laden in Pakistan. In April 2011, Obama declared his intention to seek re-election in the 2012 presidential election.",
        "race": {
            "district": {
                "demonym": "American",
                "display_name": "the United States",
                "id": "37",
                "name": "United States of America",
                "nickname": "",
                "resource_uri": "/v1/district/37/",
                "short_name": "US",
                "type": "Nation",
                "website_url": "http://www.usa.gov/"
            },
            "election_date": "2012-11-06",
            "id": "1",
            "office": {
                "branch": "Executive",
                "chamber": null,
                "executive_rank": "Primary",
                "id": "1",
                "level": "Federal",
                "resource_uri": "/v1/office/1/",
                "short_title": "President",
                "term_length": 4,
                "title": "President",
                "website_url": "http://www.whitehouse.gov/"
            },
            "resource_uri": "/v1/race/1/"
        }
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
            "limit": 20,
            "next": null,
            "offset": 0,
            "previous": null,
            "total_count": 8
        },
        "objects": [
            {
                "bio": "Born in Honolulu, Hawaii, Obama is a graduate of Columbia University and Harvard Law School, where he was the president of the Harvard Law Review. He was a community organizer in Chicago before earning his law degree. He worked as a civil rights attorney in Chicago and taught constitutional law at the University of Chicago Law School from 1992 to 2004. He served three terms representing the 13th District in the Illinois Senate from 1997 to 2004.",
                "city": "Chicago",
                "email": "",
                "facebook_username": "barackobama",
                "fax": "",
                "first_name": "Barack",
                "id": "1",
                "last_name": "Obama",
                "middle_name": "H.",
                "nickname": "Barack",
                "party": "Democratic",
                "phone": "312.698.3670",
                "race": {
                    "district": {
                        "demonym": "American",
                        "display_name": "the United States",
                        "id": "37",
                        "name": "United States of America",
                        "nickname": "",
                        "resource_uri": "/v1/district/37/",
                        "short_name": "US",
                        "type": "Nation",
                        "website_url": "http://www.usa.gov/"
                    },
                    "election_date": "2012-11-06",
                    "id": "1",
                    "office": {
                        "branch": "Executive",
                        "chamber": null,
                        "executive_rank": "Primary",
                        "id": "1",
                        "level": "Federal",
                        "resource_uri": "/v1/office/1/",
                        "short_title": "President",
                        "term_length": 4,
                        "title": "President",
                        "website_url": "http://www.whitehouse.gov/"
                    },
                    "resource_uri": "/v1/race/1/"
                },
                "resource_uri": "/v1/candidate/1/",
                "state": "IL",
                "street": "PO Box 802798",
                "twitter_username": "BarackObama",
                "website": "http://www.barackobama.com/",
                "youtube_username": "BarackObamadotcom",
                "zip": "60680"
            },
            {
                "bio": "America faces exceptional challenges. Mitt Romney is an exceptional man with unique qualifications to lead our country through perilous times, restoring our strength at home and abroad.",
                "city": "Boston",
                "email": "info@mittromney.com",
                "facebook_username": "mittromney",
                "fax": "",
                "first_name": "Willard",
                "id": "2",
                "last_name": "Romney",
                "middle_name": "Mitt",
                "nickname": "Mitt",
                "party": "Republican",
                "phone": "",
                "race": {
                    "district": {
                        "demonym": "American",
                        "display_name": "the United States",
                        "id": "37",
                        "name": "United States of America",
                        "nickname": "",
                        "resource_uri": "/v1/district/37/",
                        "short_name": "US",
                        "type": "Nation",
                        "website_url": "http://www.usa.gov/"
                    },
                    "election_date": "2012-11-06",
                    "id": "1",
                    "office": {
                        "branch": "Executive",
                        "chamber": null,
                        "executive_rank": "Primary",
                        "id": "1",
                        "level": "Federal",
                        "resource_uri": "/v1/office/1/",
                        "short_title": "President",
                        "term_length": 4,
                        "title": "President",
                        "website_url": "http://www.whitehouse.gov/"
                    },
                    "resource_uri": "/v1/race/1/"
                },
                "resource_uri": "/v1/candidate/2/",
                "state": "MA",
                "street": "PO Box 149756",
                "twitter_username": "mittromney",
                "website": "http://www.mittromney.com/",
                "youtube_username": "mittromney",
                "zip": "02114"
            },
            {
                "bio": "Governor Johnson, who has been referred to as the ‘most fiscally conservative Governor’ in the country, was the Republican Governor of New Mexico from 1994-2003.",
                "city": "Salt Lake City",
                "email": "",
                "facebook_username": "govgaryjohnson",
                "fax": "",
                "first_name": "Gary",
                "id": "11",
                "last_name": "Johnson",
                "middle_name": "",
                "nickname": "",
                "party": "Libertarian",
                "phone": "801.303.7922",
                "race": {
                    "district": {
                        "demonym": "American",
                        "display_name": "the United States",
                        "id": "37",
                        "name": "United States of America",
                        "nickname": "",
                        "resource_uri": "/v1/district/37/",
                        "short_name": "US",
                        "type": "Nation",
                        "website_url": "http://www.usa.gov/"
                    },
                    "election_date": "2012-11-06",
                    "id": "1",
                    "office": {
                        "branch": "Executive",
                        "chamber": null,
                        "executive_rank": "Primary",
                        "id": "1",
                        "level": "Federal",
                        "resource_uri": "/v1/office/1/",
                        "short_title": "President",
                        "term_length": 4,
                        "title": "President",
                        "website_url": "http://www.whitehouse.gov/"
                    },
                    "resource_uri": "/v1/race/1/"
                },
                "resource_uri": "/v1/candidate/11/",
                "state": "UT",
                "street": "731 E South Temple",
                "twitter_username": "GovGaryJohnson",
                "website": "http://www.garyjohnson2012.com/",
                "youtube_username": "govgaryjohnson",
                "zip": "84102"
            },
            {
                "bio": "As California's senior Senator, Dianne Feinstein has built a reputation as an independent voice, working with both Democrats and Republicans to find common-sense solutions to the problems facing California and the Nation.",
                "city": "San Francisco",
                "email": "",
                "facebook_username": "DianneFeinstein",
                "fax": "",
                "first_name": "Dianne",
                "id": "18",
                "last_name": "Feinstein",
                "middle_name": "",
                "nickname": "",
                "party": "Democratic",
                "phone": "",
                "race": {
                    "district": {
                        "demonym": "Californian",
                        "display_name": "the State of California",
                        "id": "42",
                        "name": "California",
                        "nickname": "The Golden State",
                        "resource_uri": "/v1/district/42/",
                        "short_name": "CA",
                        "type": "State",
                        "website_url": "http://www.ca.gov/"
                    },
                    "election_date": "2012-11-06",
                    "id": "58",
                    "office": {
                        "branch": "Legislative",
                        "chamber": "Upper",
                        "executive_rank": null,
                        "id": "2",
                        "level": "Federal",
                        "resource_uri": "/v1/office/2/",
                        "short_title": "Sen.",
                        "term_length": 6,
                        "title": "Senator",
                        "website_url": "http://www.senate.gov/"
                    },
                    "resource_uri": "/v1/race/58/"
                },
                "resource_uri": "/v1/candidate/18/",
                "state": "CA",
                "street": "",
                "twitter_username": "DianneFeinstein",
                "website": "http://www.diannefeinstein2012.com/",
                "youtube_username": "SenatorFeinstein",
                "zip": ""
            },
            {
                "bio": "For over a decade Elizabeth Emken has served as an advocate for developmentally disabled children, most recently as Vice President for Government Relations at Autism Speaks, the Nation's largest science and advocacy organization devoted to the public health emergency of autism.",
                "city": "Danville",
                "email": "info@emken2012.com",
                "facebook_username": "emken2012",
                "fax": "",
                "first_name": "Elizabeth",
                "id": "30",
                "last_name": "Emken",
                "middle_name": "",
                "nickname": "",
                "party": "Republican",
                "phone": "925.395.4475",
                "race": {
                    "district": {
                        "demonym": "Californian",
                        "display_name": "the State of California",
                        "id": "42",
                        "name": "California",
                        "nickname": "The Golden State",
                        "resource_uri": "/v1/district/42/",
                        "short_name": "CA",
                        "type": "State",
                        "website_url": "http://www.ca.gov/"
                    },
                    "election_date": "2012-11-06",
                    "id": "58",
                    "office": {
                        "branch": "Legislative",
                        "chamber": "Upper",
                        "executive_rank": null,
                        "id": "2",
                        "level": "Federal",
                        "resource_uri": "/v1/office/2/",
                        "short_title": "Sen.",
                        "term_length": 6,
                        "title": "Senator",
                        "website_url": "http://www.senate.gov/"
                    },
                    "resource_uri": "/v1/race/58/"
                },
                "resource_uri": "/v1/candidate/30/",
                "state": "CA",
                "street": "PO Box 81",
                "twitter_username": "ElizabethEmken",
                "website": "http://www.emken2012.com/",
                "youtube_username": "",
                "zip": "94526"
            },
            {
                "bio": "Ross \"Rocky\" Anderson was born in Logan, Utah in 1951. His parents, Roy and Grace Anderson, both worked at the local lumberyard, Anderson Lumber Company, which was founded by Rocky's great-grandfather, a Norwegian immigrant carpenter.",
                "city": "Salt Lake City",
                "email": "writerocky2012@gmail.com",
                "facebook_username": "YourFriendRocky",
                "fax": "",
                "first_name": "Ross",
                "id": "320",
                "last_name": "Anderson",
                "middle_name": "",
                "nickname": "Rocky",
                "party": "Other",
                "phone": "",
                "race": {
                    "district": {
                        "demonym": "American",
                        "display_name": "the United States",
                        "id": "37",
                        "name": "United States of America",
                        "nickname": "",
                        "resource_uri": "/v1/district/37/",
                        "short_name": "US",
                        "type": "Nation",
                        "website_url": "http://www.usa.gov/"
                    },
                    "election_date": "2012-11-06",
                    "id": "1",
                    "office": {
                        "branch": "Executive",
                        "chamber": null,
                        "executive_rank": "Primary",
                        "id": "1",
                        "level": "Federal",
                        "resource_uri": "/v1/office/1/",
                        "short_title": "President",
                        "term_length": 4,
                        "title": "President",
                        "website_url": "http://www.whitehouse.gov/"
                    },
                    "resource_uri": "/v1/race/1/"
                },
                "resource_uri": "/v1/candidate/320/",
                "state": "UT",
                "street": "314 W. 300 S., Suite 225",
                "twitter_username": "RockyAnderson",
                "website": "http://www.voterocky.org/",
                "youtube_username": "",
                "zip": "84101"
            },
            {
                "bio": "Dr. Jill Stein is a mother, housewife, physician, longtime teacher of internal medicine, and pioneering environmental-health advocate.",
                "city": "Madison",
                "email": "hq@jillstein.org",
                "facebook_username": "drjillstein",
                "fax": "",
                "first_name": "Jill",
                "id": "322",
                "last_name": "Stein",
                "middle_name": "Marie",
                "nickname": "",
                "party": "Green",
                "phone": "",
                "race": {
                    "district": {
                        "demonym": "American",
                        "display_name": "the United States",
                        "id": "37",
                        "name": "United States of America",
                        "nickname": "",
                        "resource_uri": "/v1/district/37/",
                        "short_name": "US",
                        "type": "Nation",
                        "website_url": "http://www.usa.gov/"
                    },
                    "election_date": "2012-11-06",
                    "id": "1",
                    "office": {
                        "branch": "Executive",
                        "chamber": null,
                        "executive_rank": "Primary",
                        "id": "1",
                        "level": "Federal",
                        "resource_uri": "/v1/office/1/",
                        "short_title": "President",
                        "term_length": 4,
                        "title": "President",
                        "website_url": "http://www.whitehouse.gov/"
                    },
                    "resource_uri": "/v1/race/1/"
                },
                "resource_uri": "/v1/candidate/322/",
                "state": "WI",
                "street": "PO Box 260217",
                "twitter_username": "jillstein2012",
                "website": "http://www.jillstein.org/",
                "youtube_username": "",
                "zip": "53726"
            },
            {
                "bio": "Jerry White, 52, has been active in the socialist movement for more than three decades.",
                "city": "",
                "email": "",
                "facebook_username": "socialism2012",
                "fax": "",
                "first_name": "Jerome",
                "id": "324",
                "last_name": "White",
                "middle_name": "",
                "nickname": "Jerry",
                "party": "Other",
                "phone": "",
                "race": {
                    "district": {
                        "demonym": "American",
                        "display_name": "the United States",
                        "id": "37",
                        "name": "United States of America",
                        "nickname": "",
                        "resource_uri": "/v1/district/37/",
                        "short_name": "US",
                        "type": "Nation",
                        "website_url": "http://www.usa.gov/"
                    },
                    "election_date": "2012-11-06",
                    "id": "1",
                    "office": {
                        "branch": "Executive",
                        "chamber": null,
                        "executive_rank": "Primary",
                        "id": "1",
                        "level": "Federal",
                        "resource_uri": "/v1/office/1/",
                        "short_title": "President",
                        "term_length": 4,
                        "title": "President",
                        "website_url": "http://www.whitehouse.gov/"
                    },
                    "resource_uri": "/v1/race/1/"
                },
                "resource_uri": "/v1/candidate/324/",
                "state": "MI",
                "street": "",
                "twitter_username": "socialism_2012",
                "website": "http://socialequality.com/",
                "youtube_username": "socialism2012",
                "zip": ""
            }
        ]
    }

