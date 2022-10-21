# Filter COMPOSITION by Archetype ID

We'll find the EHR & Composition data of a specific Archetype ID. The given archetype id is `[openEHR-EHR-COMPOSITION.encounter.v1]`

The Body Parameter:

```json
{
    "q": "SELECT e/ehr_id/value AS ehr_id, c/name/value AS composition_name, c/archetype_details/archetype_id/value as archetype_id FROM EHR e CONTAINS COMPOSITION c [openEHR-EHR-COMPOSITION.encounter.v1]"
}
```

The Response example:

```json
{
    "q": "SELECT e/ehr_id/value AS ehr_id, c/name/value AS composition_name, c/archetype_details/archetype_id/value as archetype_id FROM EHR e CONTAINS COMPOSITION c [openEHR-EHR-COMPOSITION.encounter.v1]",
    "columns": [
        {
            "path": "/ehr_id/value",
            "name": "ehr_id"
        },
        {
            "path": "/name/value",
            "name": "composition_name"
        },
        {
            "path": "/archetype_details/archetype_id/value",
            "name": "archetype_id"
        }
    ],
    "rows": [
        [
            "4b1c368a-b24f-4c02-bcdb-37bc41a02296",
            "Blood Pressure",
            "openEHR-EHR-COMPOSITION.encounter.v1"
        ],
        [
            "5a2c333e-dfe6-4764-99da-27ea941908f1",
            "Blood Pressure",
            "openEHR-EHR-COMPOSITION.encounter.v1"
        ],
        [
            "8b50006b-f232-4a7a-b364-a74822c71084",
            "Blood Pressure",
            "openEHR-EHR-COMPOSITION.encounter.v1"
        ],
        [
            "9762e3ab-84b1-4a06-86ca-04648947f689",
            "Blood Pressure",
            "openEHR-EHR-COMPOSITION.encounter.v1"
        ],
        [
            "b23652de-82e0-4edd-9d37-fcd54edaf6ce",
            "Blood Pressure",
            "openEHR-EHR-COMPOSITION.encounter.v1"
        ],
        [
            "bbd04f68-9214-4c2c-8586-ebbe8e97251a",
            "Blood Pressure",
            "openEHR-EHR-COMPOSITION.encounter.v1"
        ]
    ]
}
```
