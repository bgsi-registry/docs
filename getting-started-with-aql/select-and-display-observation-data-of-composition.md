# Select and display OBSERVATION data of COMPOSITION

Instead of displaying the EHR data or COMPOSITION data, we could display only the OBSERVATION data. This can be achieved by selecting the OBSERVATION `o`

The Body Parameter:

```json
{
    "q": "SELECT o FROM EHR e CONTAINS COMPOSITION c CONTAINS OBSERVATION o"
}
```

The Response example:

```json
{
    "q": "SELECT o FROM EHR e CONTAINS COMPOSITION c CONTAINS OBSERVATION o",
    "columns": [
        {
            "path": "o",
            "name": "#0"
        }
    ],
    "rows": [
        [
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
                        "value": "2022-04-20T13:36:50.592Z",
                        "_type": "DV_DATE_TIME"
                    },
                    "events": [
                        {
                            "name": {
                                "value": "Any event",
                                "_type": "DV_TEXT"
                            },
                            "time": {
                                "value": "2022-04-20T13:36:50.592Z",
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
                                            "magnitude": 120.0
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
                                            "magnitude": 124.0
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
                                            "value": "Sitting",
                                            "defining_code": {
                                                "_type": "CODE_PHRASE",
                                                "code_string": "at1001",
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
                                "value": "Adult",
                                "defining_code": {
                                    "_type": "CODE_PHRASE",
                                    "code_string": "at0017",
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
                    "rm_version": "1.0.4",
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
    ]
}
```
