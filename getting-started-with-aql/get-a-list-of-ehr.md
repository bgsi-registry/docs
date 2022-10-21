# Get a list of EHR

Our first query ever would be to get a list of EHR. The basic AQL for getting a list of EHR is:

```aql
SELECT e FROM EHR e
```

The structure is quite similar to SQL query. The query is about getting the data from EHR entity (like a table in a relational database) and aliased it as `e` . Then we are selecting all documents with the root path of the document, which is the `e` itself. We will get the items as a document instead of normal columns in SQL.

And here is how the above query used in the body parameter:

```json
{
    "q": "SELECT e FROM EHR e"
}
```

The example of response for the above query will be similar to this:&#x20;

```json
{
    "q": "SELECT e FROM EHR e",
    "columns": [
        {
            "path": "e",
            "name": "#0"
        }
    ],
    "rows": [
        [
            {
                "_type": "EHR",
                "ehr_id": {
                    "_type": "HIER_OBJECT_ID",
                    "value": "6f7e6f26-7209-474a-a42d-54bab923ac78"
                },
                "system_id": {
                    "_type": "HIER_OBJECT_ID",
                    "value": "openehr.bayudwiyansatria.com"
                },
                "ehr_status": {
                    "uid": {
                        "_type": "HIER_OBJECT_ID",
                        "value": "ca48b3c4-0a78-4cce-be9e-ba98d5dda790::openehr-0::1"
                    },
                    "name": {
                        "value": "EHR Status"
                    },
                    "_type": "EHR_STATUS",
                    "subject": {
                        "_type": "PARTY_SELF"
                    },
                    "is_queryable": true,
                    "is_modifiable": true,
                    "archetype_node_id": "openEHR-EHR-EHR_STATUS.generic.v1"
                },
                "time_created": {
                    "_type": "DV_DATE_TIME",
                    "value": "2022-04-17T05:43:02.569Z"
                }
            }
        ],
        [
            {
                "_type": "EHR",
                "ehr_id": {
                    "_type": "HIER_OBJECT_ID",
                    "value": "b23652de-82e0-4edd-9d37-fcd54edaf6ce"
                },
                "system_id": {
                    "_type": "HIER_OBJECT_ID",
                    "value": "openehr.bayudwiyansatria.com"
                },
                "ehr_status": {
                    "uid": {
                        "_type": "HIER_OBJECT_ID",
                        "value": "f21cd3eb-e4fe-43ff-a9ce-2369f353ac04::openehr-0::1"
                    },
                    "name": {
                        "value": "EHR Status"
                    },
                    "_type": "EHR_STATUS",
                    "subject": {
                        "_type": "PARTY_SELF"
                    },
                    "is_queryable": true,
                    "is_modifiable": true,
                    "archetype_node_id": "openEHR-EHR-EHR_STATUS.generic.v1"
                },
                "compositions": [
                    {
                        "id": {
                            "_type": "OBJECT_VERSION_ID",
                            "value": "fa9f9c00-06cc-426e-ada5-781bb6c3e942::openehr-0::1"
                        },
                        "_type": "VERSIONED_COMPOSITION",
                        "time_created": {
                            "_type": "DV_DATE_TIME",
                            "value": "2022-04-17T06:30:31.490Z"
                        }
                    }
                ],
                "time_created": {
                    "_type": "DV_DATE_TIME",
                    "value": "2022-04-17T05:52:30.576Z"
                },
                "contributions": [
                    {
                        "uid": {
                            "_type": "HIER_OBJECT_ID",
                            "value": "cf606de9-0864-41d9-bab0-c2f8c45bb830"
                        },
                        "_type": "CONTRIBUTION",
                        "audit": {
                            "_type": "AUDIT_DETAILS",
                            "committer": {
                                "name": "EHRbase Internal root",
                                "_type": "PARTY_IDENTIFIED",
                                "identifiers": [
                                    {
                                        "id": "root",
                                        "type": "EHRbase Security Authentication User",
                                        "_type": "DV_IDENTIFIER",
                                        "issuer": "EHRbase",
                                        "assigner": "EHRbase"
                                    }
                                ],
                                "external_ref": {
                                    "id": {
                                        "_type": "GENERIC_ID",
                                        "value": "dbe8656e-9251-4903-b1e3-2b31f68a79bd",
                                        "scheme": "DEMOGRAPHIC"
                                    },
                                    "type": "PARTY",
                                    "_type": "PARTY_REF",
                                    "namespace": "User"
                                }
                            },
                            "system_id": {
                                "_type": "HIER_OBJECT_ID",
                                "value": "openehr.bayudwiyansatria.com"
                            },
                            "change_type": {
                                "_type": "DV_CODED_TEXT",
                                "value": "creation",
                                "defining_code": {
                                    "_type": "CODE_PHRASE",
                                    "code_string": "249",
                                    "terminology_id": {
                                        "_type": "TERMINOLOGY_ID",
                                        "value": "openehr"
                                    }
                                }
                            },
                            "description": {
                                "_type": "DV_TEXT"
                            },
                            "time_committed": {
                                "_type": "DV_DATE_TIME",
                                "value": "2022-04-17T06:30:31.496Etc/UTC"
                            }
                        }
                    }
                ]
            }
        ]
    ]
}
```

There are 3 keys in the response: `q`, `columns`, and `rows`.

* `q` is the query sent in the request.
* `columns` has the `path` and `name` of the selection, and the position matches the list of arrays in the rows.&#x20;
* `rows` contain the data.
