==============
Batch Requests
==============

The Votizen API is designed to make data retrieval for individual objects to be
simple and intuitive. However, processing a significant amount of data requires
executing multiple HTTP requests, which is expensive and inefficient.

This may be done more efficiently by batching instructions to several
operations in a single HTTP request, which is done by constructing an array of
logical HTTP requests represented as a JSON array::

    [
        {
            "method": "GET",
            "relative_uri": "/v1/candidate/1/"
        },
        {
            "method": "GET",
            "relative_uri": "/v1/candidate/2/"
        }
    ]

To execute the instructions, pass the above data as the value of a **batch**
key in the body of a POST request to the following endpoint::

    https://api.votizen.com/v1/batch/?format=json&api_key=:api_key

Each independent operation is executed in parallel. Once all operations have
been completed,  a consolidated response of logical HTTP responses are returned
as JSON arrays::

    [
        {
            "body": {"id\": \"1\", \"is_registered_voter\": true, \"resource_uri\": \"/v1/voter/1/\", \"voter_data_uris\": {\"voter_districts_uri\": \"/v1/voter/1/districts/\", \"voter_record_uri\": \"/v1/voter/1/record/\"}
            },
            “headers”: {
                “x-ratelimit-limit”: “350”,
                “x-ratelimit-remaining”: “349”,
                “x-ratelimit-reset”: “1349467200”
            },
            "status_code": 200,
        },
        {
            "body": {"id\": \"2\", \"is_registered_voter\": true, \"resource_uri\": \"/v1/voter/2/\", \"voter_data_uris\": {\"voter_districts_uri\": \"/v1/voter/2/districts/\", \"voter_record_uri\": \"/v1/voter/2/record/\"}
            },
            “headers”: {
                “x-ratelimit-limit”: “350”,
                “x-ratelimit-remaining”: “348”,
                “x-ratelimit-reset”: “1349467200”
            },
            "status_code": 200,
        }
    ]

These are equivalent to the response one would expect from each operation if
performed as individual requests against the Votizen API.

At this time, only GET operations are available for batching. Batching should
also only be performed for independent operations: operations that are
dependent on the result of its predecessor should not be batched.


Error Handling
==============

It is possible for one of the requested operations to throw an error, which
will be encapsulated in the response as a JSON object::

    [
        {
            "body": {"message": "Your API key is invalid"},
            "status_code": 403,
        }
    ]


Limits
======

A single batch is limited to execute at most 50 requests. A batch containing
more than 50 requests will immediately fail without executing any requests.
