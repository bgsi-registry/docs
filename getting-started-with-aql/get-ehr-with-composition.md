# Get EHR with COMPOSITION

We could filter EHR list with to get only EHR with composition available. This can be achieved by adding `CONTAINS COMPOSITION c` to the query.

```aql
SELECT e FROM EHR e CONTAINS COMPOSITION c
```

The request body:

```json
{
    "q": "SELECT e FROM EHR e CONTAINS COMPOSITION c"
}
```

The Response example:

```json
{
    "q": "SELECT e FROM EHR e CONTAINS COMPOSITION c",
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
                    "value": "4b1c368a-b24f-4c02-bcdb-37bc41a02296"
                },
                "system_id": {
                    "_type": "HIER_OBJECT_ID",
                    "value": "openehr-0"
                },
                "ehr_status": {
                    "uid": {
                        "_type": "HIER_OBJECT_ID",
                        "value": "6eb55f3b-7a58-4a8d-a54a-9819c6076679::openehr-0::1"
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
                            "value": "62c18bd7-94dd-4131-bce0-cdbb816dc175::openehr-0::1"
                        },
                        "_type": "VERSIONED_COMPOSITION",
                        "time_created": {
                            "_type": "DV_DATE_TIME",
                            "value": "2022-04-17T21:31:25.485Z"
                        }
                    }
                ],
                "time_created": {
                    "_type": "DV_DATE_TIME",
                    "value": "2022-04-17T21:31:21.582Z"
                },
                "contributions": [
                    {
                        "uid": {
                            "_type": "HIER_OBJECT_ID",
                            "value": "4ab3c986-5c22-496a-a5ab-6b944efc89be"
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
                                        "value": "95691e7c-2764-4345-8ba7-d07030ed17ab",
                                        "scheme": "DEMOGRAPHIC"
                                    },
                                    "type": "PARTY",
                                    "_type": "PARTY_REF",
                                    "namespace": "User"
                                }
                            },
                            "system_id": {
                                "_type": "HIER_OBJECT_ID",
                                "value": "openehr-0"
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
                                "value": "2022-04-17T21:31:25.493Etc/UTC"
                            }
                        }
                    }
                ]
            }
        ]
    ]
}
```

