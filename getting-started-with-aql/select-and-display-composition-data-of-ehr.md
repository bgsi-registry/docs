# Select and display COMPOSITION data of EHR

Instead of displaying the EHR data, we could display only the composition data. This can be achieved by selecting the composition `c`

```
SELECT c FROM EHR e CONTAINS COMPOSITION c
```

The request body:

```json
{
    "q": "SELECT c FROM EHR e CONTAINS COMPOSITION c"
}
```

The response body example:

```json
{
    "q": "SELECT c FROM EHR e CONTAINS COMPOSITION c",
    "columns": [
        {
            "path": "c",
            "name": "#0"
        }
    ],
    "rows": [
        [
            {
                "uid": {
                    "_type": "OBJECT_VERSION_ID",
                    "value": "0ad1061b-ca34-4b5e-b1ce-acba601d3a4c::openehr-0::1"
                },
                "name": {
                    "_type": "DV_TEXT",
                    "value": "Blood Pressure"
                },
                "_type": "COMPOSITION",
                "context": {
                    "_type": "EVENT_CONTEXT",
                    "setting": {
                        "_type": "DV_CODED_TEXT",
                        "value": "primary medical care",
                        "defining_code": {
                            "_type": "CODE_PHRASE",
                            "code_string": "228",
                            "terminology_id": {
                                "_type": "TERMINOLOGY_ID",
                                "value": "openehr"
                            }
                        }
                    },
                    "start_time": {
                        "_type": "DV_DATE_TIME",
                        "value": "2022-04-16T01:31:45.308Z"
                    },
                    "participations": [
                        {
                            "mode": {
                                "_type": "DV_CODED_TEXT",
                                "value": "not specified",
                                "defining_code": {
                                    "_type": "CODE_PHRASE",
                                    "code_string": "193",
                                    "terminology_id": {
                                        "_type": "TERMINOLOGY_ID",
                                        "value": "openehr"
                                    }
                                }
                            },
                            "_type": "PARTICIPATION",
                            "function": {
                                "_type": "DV_TEXT",
                                "value": "companion"
                            },
                            "performer": {
                                "name": "Betty Bix",
                                "_type": "PARTY_RELATED",
                                "relationship": {
                                    "_type": "DV_CODED_TEXT",
                                    "value": "sister",
                                    "defining_code": {
                                        "_type": "CODE_PHRASE",
                                        "code_string": "24",
                                        "terminology_id": {
                                            "_type": "TERMINOLOGY_ID",
                                            "value": "openehr"
                                        }
                                    }
                                }
                            }
                        }
                    ]
                },
                "category": {
                    "_type": "DV_CODED_TEXT",
                    "value": "event",
                    "defining_code": {
                        "_type": "CODE_PHRASE",
                        "code_string": "433",
                        "terminology_id": {
                            "_type": "TERMINOLOGY_ID",
                            "value": "openehr"
                        }
                    }
                },
                "composer": {
                    "name": "Dr. Yamamoto",
                    "_type": "PARTY_IDENTIFIED",
                    "external_ref": {
                        "id": {
                            "_type": "HIER_OBJECT_ID",
                            "value": "3a2c3ea6-d227-44d5-a73c-5700d786af66"
                        },
                        "type": "PERSON",
                        "_type": "PARTY_REF",
                        "namespace": "DEMOGRAPHIC"
                    }
                },
                "language": {
                    "_type": "CODE_PHRASE",
                    "code_string": "en",
                    "terminology_id": {
                        "_type": "TERMINOLOGY_ID",
                        "value": "ISO_639-1"
                    }
                },
                "territory": {
                    "_type": "CODE_PHRASE",
                    "code_string": "UY",
                    "terminology_id": {
                        "_type": "TERMINOLOGY_ID",
                        "value": "ISO_3166-1"
                    }
                },
                "archetype_details": {
                    "_type": "ARCHETYPED",
                    "rm_version": "1.0.2",
                    "template_id": {
                        "_type": "TEMPLATE_ID",
                        "value": "dto.blood_pressure.v1"
                    },
                    "archetype_id": {
                        "_type": "ARCHETYPE_ID",
                        "value": "openEHR-EHR-COMPOSITION.encounter.v1"
                    }
                },
                "archetype_node_id": "openEHR-EHR-COMPOSITION.encounter.v1",
                "content": [
                    {
                        "name": {
                            "value": "Blood pressure",
                            "_type": "DV_TEXT"
                        },
                        "_type": "OBSERVATION",
                        "subject": {
                            "_type": "PARTY_SELF"
                        },
                        "encoding": {
                            "_type": "CODE_PHRASE",
                            "code_string": "UTF-8",
                            "terminology_id": {
                                "_type": "TERMINOLOGY_ID",
                                "value": "IANA_character-sets"
                            }
                        },
                        "language": {
                            "_type": "CODE_PHRASE",
                            "code_string": "en",
                            "terminology_id": {
                                "_type": "TERMINOLOGY_ID",
                                "value": "ISO_639-1"
                            }
                        },
                        "data": {
                            "name": {
                                "value": "History",
                                "_type": "DV_TEXT"
                            },
                            "origin": {
                                "value": "2022-04-16T01:31:45.358Z",
                                "_type": "DV_DATE_TIME"
                            },
                            "events": [
                                {
                                    "name": {
                                        "value": "Any event",
                                        "_type": "DV_TEXT"
                                    },
                                    "time": {
                                        "value": "2022-04-16T01:31:45.364Z",
                                        "_type": "DV_DATE_TIME"
                                    },
                                    "_type": "POINT_EVENT",
                                    "data": {
                                        "name": {
                                            "value": "blood pressure",
                                            "_type": "DV_TEXT"
                                        },
                                        "archetype_node_id": "at0003",
                                        "_type": "ITEM_TREE",
                                        "items": [
                                            {
                                                "name": {
                                                    "value": "Systolic",
                                                    "_type": "DV_TEXT"
                                                },
                                                "value": {
                                                    "_type": "DV_QUANTITY",
                                                    "units": "mm[Hg]",
                                                    "magnitude": 397.1
                                                },
                                                "_type": "ELEMENT",
                                                "archetype_node_id": "at0004"
                                            },
                                            {
                                                "name": {
                                                    "value": "Diastolic",
                                                    "_type": "DV_TEXT"
                                                },
                                                "value": {
                                                    "_type": "DV_QUANTITY",
                                                    "units": "mm[Hg]",
                                                    "magnitude": 813.6
                                                },
                                                "_type": "ELEMENT",
                                                "archetype_node_id": "at0005"
                                            }
                                        ]
                                    },
                                    "state": {
                                        "name": {
                                            "value": "state structure",
                                            "_type": "DV_TEXT"
                                        },
                                        "archetype_node_id": "at0007",
                                        "_type": "ITEM_TREE",
                                        "items": [
                                            {
                                                "name": {
                                                    "value": "Position",
                                                    "_type": "DV_TEXT"
                                                },
                                                "value": {
                                                    "_type": "DV_CODED_TEXT",
                                                    "value": "Standing",
                                                    "defining_code": {
                                                        "_type": "CODE_PHRASE",
                                                        "code_string": "at1000",
                                                        "terminology_id": {
                                                            "_type": "TERMINOLOGY_ID",
                                                            "value": "local"
                                                        }
                                                    }
                                                },
                                                "_type": "ELEMENT",
                                                "archetype_node_id": "at0008"
                                            },
                                            {
                                                "name": {
                                                    "value": "Sleep status",
                                                    "_type": "DV_TEXT"
                                                },
                                                "value": {
                                                    "_type": "DV_CODED_TEXT",
                                                    "value": "Awake",
                                                    "defining_code": {
                                                        "_type": "CODE_PHRASE",
                                                        "code_string": "at1044",
                                                        "terminology_id": {
                                                            "_type": "TERMINOLOGY_ID",
                                                            "value": "local"
                                                        }
                                                    }
                                                },
                                                "_type": "ELEMENT",
                                                "archetype_node_id": "at1043"
                                            }
                                        ]
                                    },
                                    "archetype_node_id": "at0006"
                                }
                            ],
                            "_type": "HISTORY",
                            "archetype_node_id": "at0001"
                        },
                        "protocol": {
                            "name": {
                                "value": "Tree",
                                "_type": "DV_TEXT"
                            },
                            "archetype_node_id": "at0011",
                            "_type": "ITEM_TREE",
                            "items": [
                                {
                                    "name": {
                                        "value": "Cuff size",
                                        "_type": "DV_TEXT"
                                    },
                                    "value": {
                                        "_type": "DV_CODED_TEXT",
                                        "value": "Adult Thigh",
                                        "defining_code": {
                                            "_type": "CODE_PHRASE",
                                            "code_string": "at0015",
                                            "terminology_id": {
                                                "_type": "TERMINOLOGY_ID",
                                                "value": "local"
                                            }
                                        }
                                    },
                                    "_type": "ELEMENT",
                                    "archetype_node_id": "at0013"
                                }
                            ]
                        },
                        "archetype_details": {
                            "rm_version": "1.0.2",
                            "template_id": {
                                "value": "dto.blood_pressure.v1"
                            },
                            "archetype_id": {
                                "value": "openEHR-EHR-OBSERVATION.blood_pressure.v2"
                            }
                        },
                        "archetype_node_id": "openEHR-EHR-OBSERVATION.blood_pressure.v2"
                    }
                ]
            }
        ]
    ]
}
```
