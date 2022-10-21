---
description: WIP
---

# Create a composition

A template act as a "storage" for compositions. The composition itself contains observations of the patient.

{% swagger method="post" path="/ehrbase/rest/openehr/v1/ehr/{ehr_id}/composition" baseUrl="https://ehr.portalkoding.com/ehrbase" summary="Create Composition" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

The request body:

```json
{
    "_type": "COMPOSITION",
    "archetype_node_id": "openEHR-EHR-COMPOSITION.encounter.v1",
    "name": {
        "value": "Vital Signs"
    },
    "uid": {
        "_type": "OBJECT_VERSION_ID",
        "value": "8849182c-82ad-4088-a07f-48ead4180515::openEHRSys.example.com::1"
    },
    "archetype_details": {
        "archetype_id": {
            "value": "openEHR-EHR-COMPOSITION.encounter.v1"
        },
        "template_id": {
            "value": "dto.blood_pressure.v1"
        },
        "rm_version": "1.0.2"
    },
    "language": {
        "terminology_id": {
            "value": "ISO_639-1"
        },
        "code_string": "en"
    },
    "territory": {
        "terminology_id": {
            "value": "ISO_3166-1"
        },
        "code_string": "NL"
    },
    "category": {
        "value": "event",
        "defining_code": {
            "terminology_id": {
                "value": "openehr"
            },
            "code_string": "433"
        }
    },
    "composer": {
        "_type": "PARTY_IDENTIFIED",
        "name": "Ardi kucing"
    },
    "context": {
        "_type": "EVENT_CONTEXT",
        "start_time": {
            "_type": "DV_DATE_TIME",
            "value": "2020-09-22T16:18:51.481222+02:00"
        },
        "setting": {
            "_type": "DV_CODED_TEXT",
            "value": "other care",
            "defining_code": {
                "_type": "CODE_PHRASE",
                "terminology_id": {
                    "_type": "TERMINOLOGY_ID",
                    "value": "openehr"
                },
                "code_string": "238"
            }
        },
        "health_care_facility": {
            "_type": "PARTY_IDENTIFIED",
            "exteal_ref": {
                "_type": "PARTY_REF",
                "id": {
                    "_type": "GENERIC_ID",
                    "value": "9091",
                    "scheme": "Wako Hospital"
                },
                "namespace": "Wako hospital",
                "type": "PARTY"
            },
            "name": "Wako Hospital"
        },
        "participations": [
            {
                "_type": "PARTICIPATION",
                "function": {
                    "_type": "DV_TEXT",
                    "value": "requester"
                },
                "performer": {
                    "_type": "PARTY_IDENTIFIED",
                    "exteal_ref": {
                        "_type": "PARTY_REF",
                        "id": {
                            "_type": "GENERIC_ID",
                            "value": "199",
                            "scheme": "Wako Hospital"
                        },
                        "namespace": "Wako hospital",
                        "type": "ANY"
                    },
                    "name": "Dr. Shinji Kobayashi"
                },
                "mode": {
                    "_type": "DV_CODED_TEXT",
                    "value": "face-to-face communication",
                    "defining_code": {
                        "_type": "CODE_PHRASE",
                        "terminology_id": {
                            "_type": "TERMINOLOGY_ID",
                            "value": "openehr"
                        },
                        "code_string": "216"
                    }
                }
            },
            {
                "_type": "PARTICIPATION",
                "function": {
                    "_type": "DV_TEXT",
                    "value": "performer"
                },
                "performer": {
                    "_type": "PARTY_IDENTIFIED",
                    "exteal_ref": {
                        "_type": "PARTY_REF",
                        "id": {
                            "_type": "GENERIC_ID",
                            "value": "198",
                            "scheme": "Wako Hospital"
                        },
                        "namespace": "Wako hospital",
                        "type": "ANY"
                    },
                    "name": "Nurse 1"
                },
                "mode": {
                    "_type": "DV_CODED_TEXT",
                    "value": "not specified",
                    "defining_code": {
                        "_type": "CODE_PHRASE",
                        "terminology_id": {
                            "_type": "TERMINOLOGY_ID",
                            "value": "openehr"
                        },
                        "code_string": "193"
                    }
                }
            }
        ]
    },
    "content": [
        {
            "_type": "OBSERVATION",
            "name": {
                "_type": "DV_TEXT",
                "value": "Blood pressure"
            },
            "archetype_details": {
                "archetype_id": {
                    "value": "openEHR-EHR-OBSERVATION.blood_pressure.v2"
                },
                "template_id": {
                    "value": "dto.blood_pressure.v1"
                },
                "rm_version": "1.0.4"
            },
            "language": {
                "_type": "CODE_PHRASE",
                "terminology_id": {
                    "_type": "TERMINOLOGY_ID",
                    "value": "ISO_639-1"
                },
                "code_string": "en"
            },
            "encoding": {
                "_type": "CODE_PHRASE",
                "terminology_id": {
                    "_type": "TERMINOLOGY_ID",
                    "value": "IANA_character-sets"
                },
                "code_string": "UTF-8"
            },
            "subject": {
                "_type": "PARTY_SELF"
            },
            "protocol": {
                "_type": "ITEM_TREE",
                "name": {
                    "_type": "DV_TEXT",
                    "value": "Tree"
                },
                "items": [
                    {
                        "_type": "ELEMENT",
                        "name": {
                            "_type": "DV_TEXT",
                            "value": "Cuff size"
                        },
                        "value": {
                            "_type": "DV_CODED_TEXT",
                            "value": "Paediatric/Child",
                            "defining_code": {
                                "_type": "CODE_PHRASE",
                                "terminology_id": {
                                    "_type": "TERMINOLOGY_ID",
                                    "value": "local"
                                },
                                "code_string": "at1009"
                            }
                        },
                        "archetype_node_id": "at0013"
                    }
                ],
                "archetype_node_id": "at0011"
            },
            "data": {
                "name": {
                    "_type": "DV_TEXT",
                    "value": "History"
                },
                "origin": {
                    "_type": "DV_DATE_TIME",
                    "value": "2022-05-18T02:41:15.454Z"
                },
                "events": [
                    {
                        "_type": "POINT_EVENT",
                        "name": {
                            "_type": "DV_TEXT",
                            "value": "Any event"
                        },
                        "time": {
                            "_type": "DV_DATE_TIME",
                            "value": "2022-05-18T02:41:15.454Z"
                        },
                        "state": {
                            "_type": "ITEM_TREE",
                            "name": {
                                "_type": "DV_TEXT",
                                "value": "state structure"
                            },
                            "items": [
                                {
                                    "_type": "ELEMENT",
                                    "name": {
                                        "_type": "DV_TEXT",
                                        "value": "Position"
                                    },
                                    "value": {
                                        "_type": "DV_CODED_TEXT",
                                        "value": "Standing",
                                        "defining_code": {
                                            "_type": "CODE_PHRASE",
                                            "terminology_id": {
                                                "_type": "TERMINOLOGY_ID",
                                                "value": "local"
                                            },
                                            "code_string": "at1000"
                                        }
                                    },
                                    "archetype_node_id": "at0008"
                                },
                                {
                                    "_type": "ELEMENT",
                                    "name": {
                                        "_type": "DV_TEXT",
                                        "value": "Sleep status"
                                    },
                                    "value": {
                                        "_type": "DV_CODED_TEXT",
                                        "value": "Awake",
                                        "defining_code": {
                                            "_type": "CODE_PHRASE",
                                            "terminology_id": {
                                                "_type": "TERMINOLOGY_ID",
                                                "value": "local"
                                            },
                                            "code_string": "at1044"
                                        }
                                    },
                                    "archetype_node_id": "at1043"
                                }
                            ],
                            "archetype_node_id": "at0007"
                        },
                        "data": {
                            "_type": "ITEM_TREE",
                            "name": {
                                "_type": "DV_TEXT",
                                "value": "blood pressure"
                            },
                            "items": [
                                {
                                    "_type": "ELEMENT",
                                    "name": {
                                        "_type": "DV_TEXT",
                                        "value": "Systolic"
                                    },
                                    "value": {
                                        "_type": "DV_QUANTITY",
                                        "units": "mm[Hg]",
                                        "magnitude": 22
                                    },
                                    "archetype_node_id": "at0004"
                                },
                                {
                                    "_type": "ELEMENT",
                                    "name": {
                                        "_type": "DV_TEXT",
                                        "value": "Diastolic"
                                    },
                                    "value": {
                                        "_type": "DV_QUANTITY",
                                        "units": "mm[Hg]",
                                        "magnitude": 22
                                    },
                                    "archetype_node_id": "at0005"
                                }
                            ],
                            "archetype_node_id": "at0003"
                        },
                        "archetype_node_id": "at0006"
                    }
                ],
                "archetype_node_id": "at0001"
            },
            "archetype_node_id": "openEHR-EHR-OBSERVATION.blood_pressure.v2"
        }
    ]
}
```
